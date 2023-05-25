# Python_Bi-LSTM_Attention
## 基于深度学习Python_Bi-LSTM_Attention的招聘与求职双向推荐模型
### 摘要
###### 近年来，python 作为一门编程语言，提供了高速的高级数据结构，以及简单有效地面向对象编程，随者人工智能和大数据的发展，python 逐渐成为流行 的编程语言；在新时代背景下，大学生毕业人数不断增加，大学生求职问题已成为广泛关注的社会热点。而且受疫情影响，诸多企业的招聘都改为线上进行，脱离时间和空间的限制，招聘需求不断上涨，从而出现就业竞争压力大、招聘与求职信息不对称等现象，双向职业推荐模型连接了企业与求职者的需求，利用 python语言对竞双向职业推荐模型的建立具有重大意义。
###### 通过从泰迪内推平台（https://www.5iai.com/#/index）的“找工作”页面和“找人才”页面，爬取所有招聘与求职信息并整理并形成文件：result1-1.csv以及 result1-2.csv，数据的爬取主要采用了 python 的爬虫技术。
###### 为了能准确的形成双向推荐模型我们们结合了 BI-LSTM 算法、文本匹配、Attention-LSTM 模型进行实现，基于 python 爬取得信息数据，我们对数据得空缺值处理以及异常值进行了处理，最后我们使用里 python 的 matplotlib 库、seaborn 库、对数据信息进行多个维度的用户画像，对数据之间的关系进行了数据可视化分析。基于预处理后的数据，构建岗位匹配度和求职者满意度的模型，使用 BI-LSTM 算法、文本匹配等算法，计算两表中的岗位匹配度以及满意度，每条招聘信息提供岗位匹配度非 0 的求职以及每位求职者提供求职者满意度非 0的招聘信息存放在指定的表格中。

### 章节安排
###### 根据前面相关内容的分析，我们针对用户企业双向推荐模型的研究思路主要从几节相应介绍：
###### 1） 第 3 主要介绍我们对泰迪内推网站的数据爬取过程
###### 2） 第 4 主要是介绍我们第二题的求职者以及企业多个维度的用户画像，使用matplotlib 库、seaborn 库，进行图像绘画。
###### 3） 第 5 主要介绍我们第三题的构建岗位匹配度和求职者满意度的模型，使用BI-LSTM 算法、文本匹配、Attention-LSTM 模型等

### 相关技术
##### 动态爬虫
###### 动态爬取是指爬取动态网页内容，包括通过 JavaScript 加载的内容。实现动态爬取的方法有以下几种：
###### 1. 使用 Selenium：Selenium 是一个自动化测试工具，可以模拟用户在浏览器中的操作，包括点击、输入、滚动等。通过 Selenium 可以启动一个浏览器，加载网页并执行 JavaScript，然后获取网页内容。Selenium 支持多种浏览器，包括 Chrome、Firefox、Safari 等。
###### 2. 使用 Pyppeteer：Pyppeteer 是一个 Python 库，可以通过调用 Chrome DevTools 协议来控制 Chrome 浏览器。Pyppeteer 可以启动一个 Chrome 浏览器，加载网页并执行 JavaScript，然后获取网页内容。Pyppeteer 的性能比 Selenium 更好，但需要安装 Chrome 浏览器。
###### 3. 使用 Requests-HTML：Requests-HTML 是一个 Python 库，可以发送 HTTP 请求并解析 HTML 内容。Requests-HTML 支持 JavaScript 渲染，可以通过调用浏览器引擎来执行 JavaScript，并获取渲染后的 HTML 内容。Requests-HTML 的性能比 Selenium 和 Pyppeteer 更好，但不支持所有的 JavaScript 特性。
###### 4. 使用 Splash：Splash 是一个轻量级的 JavaScript 渲染服务，可以通过 HTTP API 调用。Splash 可以启动一个浏览器，加载网页并执行 JavaScript，然后返回渲染后的 HTML 内容。Splash 支持多种浏览

##### Numpy
###### NumPy（Numerical Python）是Python的一种开源的数值计算扩展。这种工具可用来存储和处理大型矩阵，比Python自身的嵌套列表（nested list structure)结构要高效的多（该结构也可以用来表示矩阵（matrix）），支持大量的维度数组与矩阵运算，此外也针对数组运算提供大量的数学函数库。

##### Pandas
###### pandas 是基于NumPy 的一种工具，该工具是为解决数据分析任务而创建的。Pandas 纳入了大量库和一些标准的数据模型，提供了高效地操作大型数据集所需的工具。pandas提供了大量能使我们快速便捷地处理数据的函数和方法。

##### Pyecharts
######  Pyecharts是一款将python与echarts结合的强大的数据可视化工具。使用 pyecharts 可以生成独立的网页,也可以在 flask , Django 中集成使用。

##### Matplotlib 库
###### Python 开发中是专门用于开发 2D 图表(包括 3D 图表) 以渐进、交互式方式实现数据可视化，它以各种硬拷贝格式和跨平台的交互式环境生成出版质量级别的图形，可视化是在整个数据挖掘的关键辅助工具，可以清晰的理解数据，从而调整我们的分析方法。 能将数据进行可视化,更直观的呈现 使数据更加客观、更具说服力。

##### BI-LSTM 算法
###### 前向的 LSTM 与后向的 LSTM 结合成 BiLSTM[1]，结构如下图 1 所示。前向 LSTM可以获取输入序列的过去数据信息，后向 LSTM 可以获取输入序列的过去数据信息，对时间序列实现向前和向后两次 LSTM 训练，进一步提高特征提取的全局性和完整性。
###### LSTM 的全称是 Long Short-Term Memory,它是 RNN 的一种。LSTM 模型是由 t时刻的输入词 Xt，细胞状态 Ct，临时细胞状态 Ct，隐层状态 ht，遗忘门 ft ，记忆门 it，输出门 ot 组成。LSTM 的计算过程可以概括为，通过对细胞状态中信息遗忘和记忆新的信息使得对后续时刻计算有用的信息得以传递，而无用的信息被丢弃，并在每个时间步都会输出隐层状态 ht，其中遗忘、记忆与输出由通过上个时刻的隐层状态 ht−1 和 X t 当前输入计算出来的遗忘门 ft，记忆门 it，输出门 ot 来控制。总体框架如下图 2-2：

##### 文本匹配
###### 文本匹配旨在从两端文本中挖掘内在的语义特诊，预测文本间相关行或者矛盾性。文本匹配任务是自然语言处理中重要的研究方向，无论是在信息检索、问题回答还是复述识别等任务中都扮演着重要角色。传统的文本匹配方法依赖于预定义的模板和人工提取的规则。随着深度学习的发展，深度神经网络已经普遍应用于自然语言处理任务中，以节省人工提取特征所耗费的成本和时间。文本匹配任务旨在给定两段文本Ｑ和Ｄ，通过提取文本中存在的语义信息和相似度特征来给出两段文本的相似度值，由最终的相似度值可以得知两段文本的内容是否属于相似的描述。基于深度学习的文本匹配模型大致可以分为两类：基于表示的文本匹配模型和基于交互的文本匹配模型。基于表示的文本匹配模型通过对文本进行预处理以及构建索引，能够更好地提取每段文本里面的信息，但是在信息表示的过程中容易失去语义焦点，难以衡量词在上下文中的重要性。基于交互的文本匹配模型虽然可以较好地把握语义焦点，针对上下文进行更好的建模，但是却忽视了全局信息，会造成无法刻画出全局匹配信息的后果[2]

##### Attention-LSTM 模型
###### 将 LSTM 层的输出向量作为 Attention 层的输入。注意力机制的本质为计算某一特征向量的加权求和。 本文采用的是乘法注意力机制中的 ScaledDot-Product Attention 方法，其计算主要分为 3 个步骤：
###### 1. 将 query 和每个 key 进行点积计算得到权重
###### 2. 使用 Softmax 函数对权重归一化处理。
###### 3. 将权重和对应的 value 加权求和获得 Attention 。

##### tensorflow 库
###### TensorFlow 是一个基于数据流编程（dataflow programming）的符号数学系统，被广泛应用于各类机器学习（machine learning）算法的编程实现，其前身是谷歌的神经网络算法库 DistBelief。Tensorflow 拥有多层级结构，可部署于各类服务器、PC 终端和网页并支持 GPU 和 TPU 高性能数值计算，被广泛应用于谷歌内部的产品开发和各领域的科学研究 。

##### Tableau 可视化软件
###### Tableau 是能够帮助大家查看并理解数据的商业智能软件。 快速分析 在数分钟内完成数据连接和可视化。Tableau 比现有解决方案快 10 到 100 倍。 简单易用，任何人都可以使用。









