# AI资源大全

AI笔记，记录自己接触、学习、使用到的信息，持续更新...

# <span id = ''>一、深度学习</span>

## [Python用法](./Python/README.md)

| 类别     |说明     |
| ------------ |------------ |
| [综合用法](./Python/README.md) |进阶用法、文件操作|
| [numpy](./Python/NUMPY.md) |numpy用法|


## [数学知识](./数学知识/README.md)

## [深度学习](./深度学习/README.md)

---

# <span id = ''>二、模型训练</span>


| 模型     | 教程     |说明     |
| ------------ |------------ |------------ |
| [Yolo](https://docs.ultralytics.com/) |[教程]() | 目标分类、目标检测、图像分割、姿态估计|
| [PaddlePaddle](https://www.ultralytics.com/) | / | 百度飞浆的模型套件：[目标分类](https://github.com/PaddlePaddle/PaddleClas)、[目标检测](https://github.com/PaddlePaddle/PaddleDetection)、[图像分割](https://github.com/PaddlePaddle/PaddleSeg)、[NLP](https://github.com/PaddlePaddle/PaddleNLP)、[OCR](https://github.com/PaddlePaddle/PaddleOCR)、[语音](https://github.com/PaddlePaddle/PaddleSpeech/)|
| [bert-base-chinese](https://huggingface.co/google-bert/bert-base-chinese/) |[教程]() | 训练将自然语言转换成结构化数据 |


# <span id = ''>三、移动端</span>

| 类别     |说明     |
| ------------ |------------ |
| [移动端模型部署](./移动端/移动端模型部署.md) |模型转换为移动端格式|
| [C++](./移动端/C++.md) |C++使用记录，主要用于封装跨平台逻辑|
| [native集成opencv](./移动端/native集成opencv.md) |android native集成使用opencv|



# <span id = ''>四、智能体</span>


| 网站     | 教程   |说明                                             |
| ------------ | ---------| ------------------------------------------------------------ |
|[Langchain](https://www.langchain.com/)<br>[中文网1](https://www.langchain.com.cn/)<br>[中文网2](https://langchaincn.com/)|[教程](./Agent/langchain/README.md)| 通过提供丰富的组件库和统一的模型接口来简化LLM应用的开发流程，<br>采用链式结构将多个LLM调用和工具调用有序链接，形成单向流动的任务序列，适合处理预定义的线性工作流|
|[LangGraph](https://langchain-ai.github.io/langgraph/) |[教程](./Agent/langchain/README.md)|LangChain生态中专用于构建有状态多智能体系统的库，采用图结构支持循环、<br>回溯等复杂控制流通过中央状态组件确保上下文的连续性，特别适用于需要动态交互和多智能体协作的复杂应用|


# <span id = ''>五、AI资源</span>


| 网站     | 类别   |说明                                             |
| ------------ | -----| ------------------------------------------------------------ |
|[AIStudio](https://aistudio.baidu.com/my/learn) |学习社区| AI Studio是百度飞桨推出的‌人工智能学习与实训社区‌，提供从学习到实践的一站式AI开发服务|
|[‌Hugging Face](https://huggingface.co) |模型托管| 提供各类开源预训练模型托管、API及社区支持，适合快速上手大模型开发‌|
|[Langchain](https://www.langchain.com/)<br>[中文网](https://www.langchain.com.cn/)|LLM开发框架| 以“链”（Chain）为核心，通过预定义顺序组合LLM调用、工具调用和数据源，形成线性或简单分支的工作流，架构遵循有向无环图（DAG）功能特点：提供统一接口集成多种LLM（如OpenAI、Claude）、支持RAG、Agent、Memory管理等模块化组件、适合标准化流程（如客服机器人、数据检索）|
|[LangGraph](https://langchain-ai.github.io/langgraph/) |LLM开发框架| 基于图（Graph）结构，支持循环、条件分支和状态管理，节点代表操作步骤，边定义动态流转逻辑。功能特点：中央状态（State）管理，适用于多智能体协作、支持循环回溯，处理复杂交互（如金融风控系统）、与LangChain兼容，可嵌套使用其链作为节点|
|[‌Dify](https://docs.dify.ai/zh-hans/introduction) |Agent平台| Dify 是一款开源的大语言模型（LLM）应用开发平台，融合了后端即服务和LLMOps的理念，旨在帮助开发者快速搭建生产级的生成式 AI 应用|
|[Copilotkit](https://www.copilotkit.ai/) |AI助手开发框架| 用于快速将 AI 功能集成到应用程序中‌它提供标准化 API 和 React UI 组件，支持构建应用内 AI 聊天机器人、智能文本编辑器等场景，并能通过 LangChain 技术实现自动化任务处理‌|
|[Claude Code](https://claude.com/product/claude-code/) |AI编程助手| 专注于代码生成、重构和跨文件修改等开发任务，强调终端环境的自主执行能力。擅长代码解释、自动补全和错误修复，尤其适合复杂工程任务|
|[MCP](https://claude.com/product/claude-code/) |模型协议| [百度MCP](https://www.mcpworld.com/mcp)、[阿里云MCP](https://bailian.console.aliyun.com/?tab=mcp#/mcp-market)|

<br>
<br>


| AI训练平台     |说明                                              |
| ---------------------- |---------------------------------------- |
|[EasyDL](https://ai.baidu.com/easydl/) |百度的零门槛AI开发平台，支持步骤化的AI训练|
|[TI-ONE](https://cloud.tencent.com/document/product/851/) |腾讯的全栈式人工智能开发服务平台，致力于打通包含从数据获取、数据处理、算法构建、模型训练、模型评估、模型部署、到 AI 应用开发的产业 + AI 落地全流程链路，帮助用户快速创建和部署 AI 应用|


# <span id = ''>六、在线模型</span>

### 语言模型

| 模型     | 说明     |
| ------------ | ------------ |
|  [DeepSeek](https://chat.deepseek.com/)| 语言大模型 |
|  [阿里云通义千问](https://bailian.console.aliyun.com/?tab=model#/efm/model_experience_center/text)| 语言大模型 |
|  [文心一言](https://yiyan.baidu.com/?utmSource=pinzhuan)| 语言大模型 |
|  [腾讯元宝](https://yuanbao.tencent.com/chat/naQivTmsDa?yb_channel=3003)| 语言大模型 |

### 视觉模型

| 模型     |说明     |
| ------------ |------------ |
| [DINO-X](https://cloud.deepdataspace.com/zh/playground/dino-x?referring_prompt=0)| 覆盖目标检测、关键点检测、图像描述等多种视觉能力，支持文本提示、视觉提示和无需提示，通过端到端的 API 服务，让视觉感知更智能、更高效|
| [阿里云通义千问](https://bailian.console.aliyun.com/?tab=model#/efm/model_experience_center/vision)| 视觉大模型 |

### 语音模型

| 模型     |说明     |
| ------------ |------------ |
| [阿里云Paraformer](https://bailian.console.aliyun.com/?tab=model#/efm/model_experience_center/voice)| 语音大模型 |



---

# <span id = ''>七、实战项目</span>

智能体在项目中的实际应用

飞镖识别

UI自动化测试

二维码识别

---

# <span id = ''>八、AI面试</span>

1.  [深度学习基础常见面试题](https://paddlepedia.readthedocs.io/en/latest/tutorials/interview_questions/interview_questions.html)
2. [卷积模型常见面试题](https://paddlepedia.readthedocs.io/en/latest/tutorials/interview_questions/interview_questions.html#id2)
3. [预训练模型常见面试题](https://paddlepedia.readthedocs.io/en/latest/tutorials/interview_questions/interview_questions.html#id3)
4. [对抗神经网络常见面试题](https://paddlepedia.readthedocs.io/en/latest/tutorials/interview_questions/interview_questions.html#id4)
5. [计算机视觉常见面试题](https://paddlepedia.readthedocs.io/en/latest/tutorials/interview_questions/interview_questions.html#id5)
6. [自然语言处理常见面试题](https://paddlepedia.readthedocs.io/en/latest/tutorials/interview_questions/interview_questions.html#id6)
7. [推荐系统常见面试题](https://paddlepedia.readthedocs.io/en/latest/tutorials/interview_questions/interview_questions.html#id7)
8.  [模型压缩常见面试题](https://paddlepedia.readthedocs.io/en/latest/tutorials/interview_questions/interview_questions.html#id8)
9.  [强化学习常见面试题](https://paddlepedia.readthedocs.io/en/latest/tutorials/interview_questions/interview_questions.html#id9)
