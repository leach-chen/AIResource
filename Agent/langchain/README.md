```
pip install langchain langchain-openai

from langchain_core.chat_history import BaseChatMessageHistory, InMemoryChatMessageHistory
from langchain_core.messages import SystemMessage, HumanMessage
from langchain_core.output_parsers import StrOutputParser
from langchain_core.prompts import ChatPromptTemplate, MessagesPlaceholder
from langchain_core.runnables import RunnableWithMessageHistory
from langchain_openai import ChatOpenAI

model = ChatOpenAI(model="qwen3-max",base_url="https://dashscope.aliyuncs.com/compatible-mode/v1",api_key="xxx")

store = {}
def get_session_history(session_id: str) -> BaseChatMessageHistory:
    if session_id not in store:
        store[session_id] = InMemoryChatMessageHistory()
    return store[session_id]

prompt = ChatPromptTemplate.from_messages(
    [
        (
            "system",
            "You are a helpful assistant. Answer all questions to the best of your ability in {language}.",
        ),
        MessagesPlaceholder(variable_name="messages"),
    ]
)
chain = prompt | model | StrOutputParser()
with_message_history = RunnableWithMessageHistory(chain,get_session_history,input_messages_key="messages")

for r in with_message_history.stream(
    {
        "messages": [HumanMessage(content="hi! I'm todd. tell me a joke")],
        "language": "Chinese",
    },
    config=config,
):
    print(r, end="|")
```



```
pip install langchain langchain-chroma langchain-openai
```


```
from langchain_chroma import Chroma
from langchain_core.prompts import ChatPromptTemplate
from langchain_core.runnables import RunnablePassthrough, RunnableLambda
from langchain_openai import ChatOpenAI, OpenAIEmbeddings
from langchain_core.documents import Document

model = ChatOpenAI(model="qwen3-max",base_url="https://dashscope.aliyuncs.com/compatible-mode/v1",api_key="xxx")

documents = [
    Document(
        page_content="Dogs are great companions, known for their loyalty and friendliness.",
        metadata={"source": "mammal-pets-doc"},
    ),
    Document(
        page_content="Cats are independent pets that often enjoy their own space.",
        metadata={"source": "mammal-pets-doc"},
    ),
    Document(
        page_content="Goldfish are popular pets for beginners, requiring relatively simple care.",
        metadata={"source": "fish-pets-doc"},
    ),
    Document(
        page_content="Parrots are intelligent birds capable of mimicking human speech.",
        metadata={"source": "bird-pets-doc"},
    ),
    Document(
        page_content="Rabbits are social animals that need plenty of space to hop around.",
        metadata={"source": "mammal-pets-doc"},
    ),
]

vectorstore = Chroma.from_documents(
    documents,
    embedding=OpenAIEmbeddings(model="qwen2.5-vl-embedding",base_url="https://dashscope.aliyuncs.com/compatible-mode/v1",api_key="xxx"),
)

#vectorstore.similarity_search("cat")
#retriever = RunnableLambda(vectorstore.similarity_search).bind(k=1)  # select top result
#retriever.batch(["cat", "shark"])

retriever = vectorstore.as_retriever(
    search_type="similarity",
    search_kwargs={"k": 1},
)

#print(vectorstore.similarity_search("cat"))
message = """
Answer this question using the provided context only.

{question}

Context:
{context}
"""

prompt = ChatPromptTemplate.from_messages([("human", message)])

rag_chain = {"context": retriever, "question": RunnablePassthrough()} | prompt | model

response = rag_chain.invoke("tell me about cats")
print(response.content)
```


 ```
 import os

from langchain_anthropic import ChatAnthropic
from langchain_community.tools.tavily_search import TavilySearchResults
from langchain_openai import ChatOpenAI
from langchain_tavily import TavilySearch
from langchain_core.messages import HumanMessage
from langgraph.checkpoint.memory import MemorySaver
from langchain.agents import create_agent


os.environ["ANTHROPIC_API_KEY"] = "xxx"


# Create the agent
memory = MemorySaver()
model = ChatOpenAI(model="qwen-plus",base_url="https://dashscope.aliyuncs.com/compatible-mode/v1",api_key="xxx")
search = TavilySearch(max_results=2,tavily_api_key="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")
tools = [search]
agent_executor = create_agent(model, tools, checkpointer=memory)

# Use the agent
config = {"configurable": {"thread_id": "abc123"}}
for chunk in agent_executor.stream(
    {"messages": [HumanMessage(content="hi im bob! and i live in sf")]}, config
):
    print(chunk)
    print("----")

for chunk in agent_executor.stream(
    {"messages": [HumanMessage(content="whats the weather where I live?")]}, config
):
    print(chunk)
    print("----")

 ```