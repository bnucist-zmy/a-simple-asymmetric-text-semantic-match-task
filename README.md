### Task：非对称文本匹配

#### 1、任务描述

* 非对称文本匹配：指两个内容表述和篇幅具有较大差异但语义相似的文本之间的匹配任务
* Task：给定**(question, sentence)**的pair，判断sentence中是否包含该question的正确答案，其中question和sentence之间为**非对称文本**（sentence的单词数目至少为question的5倍）

#### 2、数据集

* 数据来源：某公开数据集上筛选得到的非对称文本

* 数据样例

  > label : 1
  >
  > question : *What city was FIFA formed?*
  >
  > sentence : *"FIFA, the international football body, was formed in Paris in 1904 and declared that they would adhere to Laws of the Game of the Football Association."*

  >label : 0
  >
  >question : *When was the University of Valencia founded?*
  >
  >sentence : *"Some of the most emblematic buildings of the city were built during this period, including the Serranos Towers (1392), the Lonja (1482), the Miguelete and the Chapel of the Kings of the Convent of Santo Domingo.*

* 数据集构成

  > 训练集：train.csv ，包含8k文本数据
  >
  > 测试集：test.csv，包含1.6k文本数据
  >
  > 正样例和负样例的数目比值接近1 : 1

#### 3、测评

* eval.py文件

  > Input : test.csv , pred.csv
  >
  > Output : accuracy

* 测评说明

  > pred.csv是模型处理测试数据test.csv得到的预测结果，不同之处在于pred.csv第1列的label是模型输出的结果
  >
  > 以accuracy作为评价模型性能的标准

