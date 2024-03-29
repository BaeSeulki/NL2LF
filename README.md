## NL2LF 
___(持续更新中...)___   
**_recently update log:_**  

_0. UnifiedSKG, UniSAr_  
_1. GNN works: LGESQL, ShadowGNN, SADGA, S²SQL (SOTA)_   
_2. RatSQL + Pretraining (STRUG, GraPPa, GAP, GP) + NatSQL_   
_3. PICARD, DT-Fixup, RaSaP_  
_4. wikisql: SeaD, SeqGenSQL, BRIDGE^_   




> The Resources for `Natural Language to Logical Form` Research, Focus on `NL2SQL` first.  
> "自然语言转逻辑形式"研究资料收集: 
> 本阶段主要以**NL2SQL**的研究为主, 主要包括评测公开数据集、相关论文和部分代码实现、相关博客或公众号文章。

[NL2SQL](#nl2sql--text2sql)  
[一、主要评测数据集 dataset](#一主要评测数据集dataset)  
[二、主要论文方法及代码实现 papers&code](#二主要论文方法及代码实现paperscode)  
&nbsp;&nbsp;&nbsp;&nbsp;[1. WikiSQL](#1-wikisql)  
&nbsp;&nbsp;&nbsp;&nbsp;[2. Spider](#2-spider)  
&nbsp;&nbsp;&nbsp;&nbsp;[3. UnifiedSKG](#3-unifiedskg--)   
[三、相关资源扩展 extend-resources](#三相关资源扩展-extend-resources)  
&nbsp;&nbsp;&nbsp;&nbsp;[1. Related Works](#1-related-works)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.1. Pre-training](#11-pre-training--)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.2. Systems](#12-systems)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.3. Surveys](#13-surveys)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.4. Blogs](#14-blogs)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.5. Other Papers](#15-other-papers)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.6. Tools](#16-tools)  
&nbsp;&nbsp;&nbsp;&nbsp;[2. SQL2Seq](#2-sql2seq)  
&nbsp;&nbsp;&nbsp;&nbsp;[3. 图神经网络 GNN](#3-图神经网络gnn)  


### NL2SQL & Text2SQL
#### 一、主要评测数据集(DataSet)
---
- **Academic, Advising, ATIS, Geography, Restaurants, Scholar, IMDB, Yelp, etc.**  
  + `Blog` [http://jkk.name/text2sql-data/](http://jkk.name/text2sql-data/) 
  + `GitHub` [https://github.com/jkkummerfeld/text2sql-data](https://github.com/jkkummerfeld/text2sql-data)
  + `Paper` [Improving Text-to-SQL Evaluation Methodology](https://www.aclweb.org/anthology/P18-1033.pdf), _Finegan-Dollak C, Kummerfeld J K, Zhang L, et al._, ACL 2018  
---

- **WikiTableQuestions**
  + `Home`  [WikiTableQuestions: a Complex Real-World Question Understanding Dataset](https://nlp.stanford.edu/blog/wikitablequestions-a-complex-real-world-question-understanding-dataset/)

---
- **WikiSQL**  
  > WikiSQL数据集特点:
  > 1. 单表单列查询; 
  > 2. 聚合操作('MAX', 'MIN', 'COUNT', 'SUM', 'AVG'); 
  > 3. 条件连接('AND'); 
  > 4. 条件比较('=', '>', '<')
  + `GitHub` [https://github.com/salesforce/WikiSQL](https://github.com/salesforce/WikiSQL)
  + `Paper` [Seq2sql: Generating structured queries from natural language using reinforcement learning](https://arxiv.org/pdf/1709.00103.pdf), _Zhong V, Xiong C, Socher R._ , 2017.

---
- **Spider**  
  > Spider数据集特点:
  > 1. Complex, Cross-domain and Zero-shot 
  > 2. 多表多列查询, 复杂子查询;
  > 3. 聚合操作('MAX', 'MIN', 'COUNT', 'SUM', 'AVG','GROUP', 'HAVING', 'LIMIT'); 
  > 4. join连接：('join', 'on', 'as')
  > 5. where连接：('AND','OR'); 
  > 6. where操作：('not', 'between', '=', '>', '<', '>=', '<=', '!=', 'in', 'like', 'is', 'exists')
  > 7. 排序操作：('order by', 'desc', 'asc')
  > 8. sql连接：('Intersect', 'Union', 'Except')
  + `Home` [https://yale-lily.github.io/spider](https://yale-lily.github.io/spider)
  + `GitHub` [https://github.com/taoyds/spider](https://github.com/taoyds/spider)
  + `Paper` [Spider: A Large-Scale Human-Labeled Dataset for Complex and Cross-Domain Semantic Parsing and Text-to-SQL Task](https://arxiv.org/pdf/1809.08887.pdf) _Yu T, Zhang R, Yang K, et al._ , EMNLP 2018.
  + `PPT` [spider/wikisql/tableQA数据集统计对比_by gibbsxiong](PPT/三个数据集统计分析.pptx)

---
- **SParC**
  > SParC数据集特点:
  > 1. Context-dependent and Multi-turn version of the Spider task.  
       继承Spider特点的上下文多轮任务。
  + `Home` [https://yale-lily.github.io/sparc](https://yale-lily.github.io/sparc)
  + `Paper`[SParC: Cross-Domain Semantic Parsing in Context](https://arxiv.org/pdf/1906.02285.pdf), _Yu T, Zhang R, Yasunaga M, et al._, ACL 2019.

---
- **CoSQL**
  > CoSQL数据集特点: 
  > 1. Cross-domain Conversational, the Dilaogue version of the Spider and SParC tasks.  
  >    继承Spider特点的多轮对话任务，涉及意图澄清。
  + `Home` [https://yale-lily.github.io/cosql](https://yale-lily.github.io/cosql)
  + `Paper` [CoSQL: A Conversational Text-to-SQL Challenge Towards Cross-Domain Natural Language Interfaces to Databases](https://arxiv.org/pdf/1909.05378.pdf), _Yu T, Zhang R, Er H Y, et al._, EMNLP-IJCNLP 2019. 

---
- **Chinese Spider**
  > 中文版Spider  
  + `Home` [https://taolusi.github.io/CSpider-explorer/](https://taolusi.github.io/CSpider-explorer/)
  + `GitHub` [https://github.com/taolusi/chisp](https://github.com/taolusi/chisp)
  + `Paper` [A Pilot Study for Chinese SQL Semantic Parsing](https://frcchang.github.io/pub/emnlp2019.2.pdf), _Qingkai Min, Yuefeng Shi and Yue Zhang_, EMNLP-IJCNLP 2019.

---
- **TableQA** 
  > 首届中文NL2SQL挑战赛 
  > 数据特点:
  > 1. 中文加强版WikiSql，金融等泛领域数据
  > 2. 单表多列(两列)查询
  > 3. 聚合操作('MAX', 'MIN', 'COUNT', 'SUM', 'AVG'); 
  > 4. 条件连接('AND', 'OR'); 
  > 5. 条件比较('=', '>', '<', '!=')
  + `Home` [https://tianchi.aliyun.com/competition/entrance/231716/information](https://tianchi.aliyun.com/competition/entrance/231716/information)
  + `GitHub` [https://github.com/ZhuiyiTechnology/nl2sql_baseline](https://github.com/ZhuiyiTechnology/nl2sql_baseline)
  + `Paper` [TableQA: a Large-Scale Chinese Text-to-SQL Dataset for Table-Aware SQL Generation](https://arxiv.org/pdf/2006.06434.pdf)[J]. Sun N, Yang X, Liu Y. 2020.
  + `Blog` 
    1. [人工智能时代如何高效发掘数据库的价值？NL2SQL值得你关注](https://www.jiqizhixin.com/articles/2019-06-02-3)
    2. [让机器自动写SQL语言，首届中文NL2SQL挑战赛等你来战](https://mp.weixin.qq.com/s/wuC8O6DuxxtuFe8BO1ilZQ)
    3. [一图读懂首届中文NL2SQL挑战赛](https://mp.weixin.qq.com/s/0FhfX0r643umZ36HxffLmQ)
    4. [基于Bert的NL2SQL模型：一个简明的Baseline_苏剑林](https://kexue.fm/archives/6771)
    5. [首届中文NL2SQL挑战赛圆满结束，产学研携手共推智能交互发展](https://mp.weixin.qq.com/s/F747u_n3vVC2y8Z1dOaoNw)
  + `RANK` 
    1. [冠军方案_MSQL_Top1.pdf](PPT/Top1.pdf) 
       [https://github.com/nudtnlp/tianchi-nl2sql-top1](https://github.com/nudtnlp/tianchi-nl2sql-top1)
    2. [亚军方案_top2.pdf](PPT/top2.pdf)
    3. [季军方案_top3.pdf](PPT/top3.pdf)
       第三名代码实现 [https://github.com/beader/tianchi_nl2sql](https://github.com/beader/tianchi_nl2sql)
    4. [第四名方案_top4.pdf](PPT/top4.pdf)
    5. [第五名方案_top5.pdf](PPT/top5.pdf)
    6. 第六名代码实现 [https://github.com/eguilg/nl2sql](https://github.com/eguilg/nl2sql)
  + `Paper`   
    1. Zhang X, Yin F, Ma G, et al. [M-SQL: Multi-Task Representation Learning for Single-Table Text2sql Generation](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9020099)[J]. IEEE Access, 2020, 8: 43156-43167. 🔥

---
- **DuSQL**  
  > 百度2020语言与智能技术竞赛：语义解析任务，大规模开放领域的复杂中文Text-to-SQL数据集
  > 数据特点：
  > 1. 包含200个Database以及对应的2.3万对(question, SQL query)，其中18000对用于训练集，2000用于验证集，3000用于测试集。
  > 2. 200个Database来自百科infobox、百科表格数据、以及互联网上存在的表格数据。每个Database包含若干张表格（2-11张，平均4.1张），人工构建了表之间的链接操作（即foreign key）。为了验证解析算法Database无关性及question无关性，在训练集合和测试集合的Database无交叉。
  > 3. 包含复杂的多表join查询和嵌套查询，复杂度和spider类似。评价方法关注每一个组件的精准匹配度，并消除顺序影响。因此对val的准确度要求更高。具体的sql嵌套结构单元分解如下：

  ``` shell
  # 关键词和嵌套规则
  select: [(agg_id, val_unit), (agg_id, val_unit), ...]
  from: {'table_units': [table_unit, table_unit, ...], 'conds': condition}
  where: condition
  groupBy: [col_unit, ...]
  orderBy: asc/desc, [(agg_id, val_unit), ...]
  having: condition
  limit: None/number
  intersect: None/sql
  except: None/sql 
  union: None/sql
  ```
  ```shell
  # 连接单元
  val: number(float)/string(str)/sql(dict)
  col_unit: (agg_id, col_id)
  val_unit: (calc_op, col_unit1, col_unit2)
  table_type: 'table_unit'/'sql'
  table_unit: (table_type, table_id/sql)
  cond_unit: (agg_id, cond_op, val_unit, val1, val2)
  condition: [cond_unit1, 'and'/'or', cond_unit2, ...]
  ```
  ```shell
  # op操作符
  agg_id: (none, max, min, count, sum, avg)
  calc_op: (none, -, +, \*, /)
  cond_op: (not_in, between, =, >, <, >=, <=, !=, in, like)
  ```
  + `Home` [https://aistudio.baidu.com/aistudio/competition/detail/30?isFromCcf=true](https://aistudio.baidu.com/aistudio/competition/detail/30?isFromCcf=true)    
  + `GitHub` [https://github.com/PaddlePaddle/Research/tree/master/NLP/DuSQL-Baseline](https://github.com/PaddlePaddle/Research/tree/master/NLP/DuSQL-Baseline)
  + `Video` 冠军分享  [http://mbd.baidu.com/webpage?type=live&action=liveshow&source=h5pre&room_id=4008201814](http://mbd.baidu.com/webpage?type=live&action=liveshow&source=h5pre&room_id=4008201814)
  + `Paper` 
     - [ ] Wang L, Zhang A, Wu K, et al. [DuSQL: A Large-Scale and Pragmatic Chinese Text-to-SQL Dataset](https://www.aclweb.org/anthology/2020.emnlp-main.562.pdf)[C]//Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing (EMNLP). 2020: 6923-6935.  
  + `Dataset`
     [https://github.com/luge-ai/luge-ai/blob/master/semantic-parsing/semantic-parsing.md](https://github.com/luge-ai/luge-ai/blob/master/semantic-parsing/semantic-parsing.md)
  +  `Blog`  
     1. [“语义解析”任务FAQ](https://mp.weixin.qq.com/s/EXS1dgGzAyttAeHwWjrt2A)   
     2. [语义解析 (Text-to-SQL) 技术研究及应用 上篇](https://mp.weixin.qq.com/s/FtsA4O_VTUqhhYS3Gq3G8Q)  
     3. [语义解析 (Text-to-SQL) 技术研究及应用 下篇](https://mp.weixin.qq.com/s/5lTLW5OOuRMo2zjbzMxr_Q)  
     4. [UNIT结构化知识问答产品](https://ai.baidu.com/forum/topic/show/957042)  

---
- **CCKS2022：金融NL2SQL评测**
  > 现有NL2SQL数据和方法主要关注“封闭场景指定库/表”设定，这很难满足业务范围动态发展的需求。从领域特性来看，金融数据多为时间序列，包括日频行情、季频财报、年度GDP、不定期股票质押解质押等，这无疑会增大问题转SQL难度。

+ `Home` [https://www.biendata.xyz/competition/fin_nl2sql/](https://www.biendata.xyz/competition/fin_nl2sql/)
+ `DOC` [评测任务书-金融NL2SQL评测任务](http://sigkg.cn/ccks2022/wp-content/uploads/2022/04/CCKS2022-%E9%87%91%E8%9E%8DNL2SQL.docx)


#### 二、主要论文方法及代码实现（Papers&Code）
> 论文主要以WikiSQL和Spider为评测数据，相应排行榜详见任务主页。  
> 下面主要整理具有代表性的方法，持续更新补充...  
> 注: 
> Exe_score 表示 | model | Dev accuracy |  Test accuracy  |，表示执行准确率(Execution accuracy)  
> Log_score 表示逻辑准确率(Logical accuracy)，且Spider中不包括值预测。

#### **`1. WikiSQL:`** 
- **`Weakly Supervised`**  
  > 采用弱监督方法，即不使用sql的逻辑形式作为监督信号。 

  `Paper`
  - [ ] Li N, Keller B, Butler M, et al. [SeqGenSQL--A Robust Sequence Generation Model for Structured Query Language](https://arxiv.org/pdf/2011.03836.pdf)[J]. 2020. 🔥
  - [ ] Min S, Chen D, Hajishirzi H, et al. [A discrete hard em approach for weakly supervised question answering](https://www.cs.princeton.edu/~danqic/papers/emnlp2019.pdf)[C]. EMNLP-IJCNLP 2019.  
  - [ ] Wang B, Titov I, Lapata M. [Learning Semantic Parsers from Denotations with Latent Structured Alignments and Abstract Programs](https://arxiv.org/pdf/1909.04165.pdf). 2019.
  - [ ] Agarwal R, Liang C, Schuurmans D, et al. [Learning to Generalize from Sparse and Underspecified Rewards](https://arxiv.org/pdf/1902.07198.pdf). 2019.  
  - [ ] Liang C, Norouzi M, Berant J, et al. [Memory augmented policy optimization for program synthesis and semantic parsing](https://papers.nips.cc/paper/8204-memory-augmented-policy-optimization-for-program-synthesis-and-semantic-parsing.pdf)[C].NeurIPS, 2018: 9994-10006.
  - [ ] Guo T, Gao H. [Using Database Rule for Weak Supervised Text-to-SQL Generation](https://arxiv.org/pdf/1907.00620.pdf)[J]. 2019.


  `Code` 
  - Hard-EM [https://github.com/shmsw25/qa-hard-em](https://github.com/shmsw25/qa-hard-em) 🔥 
  - LatentAlignment [https://github.com/berlino/weaksp_em19](https://github.com/berlino/weaksp_em19)
  - MeRL / MAPO [https://github.com/google-research/google-research/tree/master/meta_reward_learning](https://github.com/google-research/google-research/tree/master/meta_reward_learning)
  - Rule-SQL [https://github.com/guotong1988/Rule-SQL](https://github.com/guotong1988/Rule-SQL)

  `Exe_score`  

  |Hard-EM|84.4 |  83.9  |
  |-|-|-|
  |LatentAlignment| 79.4 | 79.3 |
  |MeRL | 74.9 | 74.8 |
  |MAPO | 72.2 | 72.1 |
  |Rule-SQL| 61.1 | 61.0 |

---
---
- **`ExecutionGuided`**  
  > Execution Guided (EG) 可以在解码阶段通过执行错误对生成sql的项进行修正,从而过滤了一些不符合实际的sql语句。主要分为三类执行错误：1）句法解析错误，即生成的sql语法错误。2）执行失败。常见的run-time error, 例如SUM( ) 和比较string类型的数据；3）假设执行结果不为空，则空查询的条件错误。例如条件值实际并不存在于预测的列中, 因此会去 Beam Search 实际包含条件值的列。

  `Paper`  
  - [ ]  Wang C, Huang P S, Polozov A, et al. [Robust Text-to-SQL Generation with Execution-Guided Decoding](https://arxiv.org/pdf/1807.03100.pdf)[J]. 2018.  
  - [ ]  Wang C, Brockschmidt M, Singh R. [Pointing out SQL queries from text](https://openreview.net/pdf?id=BkUDW_lCb)[J]. 2018. 
  - [ ]  Dong L, Lapata M. [Coarse-to-fine decoding for neural semantic parsing](https://arxiv.org/pdf/1805.04793.pdf)[J]. 2018.
  - [ ]  Huang P S, Wang C, Singh R, et al. [Natural language to structured query generation via meta-learning](https://arxiv.org/pdf/1803.02400.pdf)[J]. 2018.


  `Code`  
  - [https://github.com/microsoft/PointerSQL](https://github.com/microsoft/PointerSQL)  
  - [https://github.com/donglixp/coarse2fine](https://github.com/donglixp/coarse2fine)  

  `Exe_score`  

  |Coarse2Fine + EG| 84.0 | 83.8 |
  |-|-|-|
  | Coarse2Fine | 79.0 | 78.5 |
  | Pointer-SQL + EG | 78.4 |  78.3  |
  | Pointer-SQL | 72.5 | 71.9 |

---
---

- **`SQLNet Framework`**  
  > 设计了一种满足SQL语法的框架, 在这样的语法框架内，只需要预测并填充相应的槽位。
  > 语法框架为：
  > ```
  > SELECT $AGG $COLUMN
  > WHERE $COLUMN $OP $VALUE
  > (AND $COLUMN $OP $VALUE)*
  > ```
  > 在这基础上去完成不同的联合任务的分类预测：
  > 1) select-column, 选择的列
  > 2) select-aggregation， 聚合操作类型
  > 3) where-number， where条件语句的数量
  > 4) where-column， where条件中的列
  > 5) where-operator， where条件操作类型（'<','=','>'）
  > 6) where-value， where条件值

  `Paper`  
  - [ ]  Xu X, Liu C, Song D. [SQLNet: Generating structured queries from natural language without reinforcement learning](https://arxiv.org/pdf/1711.04436.pdf)[J]. 2018.  
  - [ ]  Hwang W, Yim J, Park S, et al. [A Comprehensive Exploration on WikiSQL with Table-Aware Word Contextualization](https://arxiv.org/pdf/1902.01069.pdf)[J]. 2019.  
  - [ ]  He P, Mao Y, Chakrabarti K, et al. [X-SQL: reinforce schema representation with context](https://arxiv.org/pdf/1908.08113.pdf)[J]. 2019. 🔥
  - [ ]  Tong Guo, Huilin Gao. [Content Enhanced BERT-based Text-to-SQL Generation ](https://arxiv.org/pdf/1910.07179.pdf).2019.
  - [ ]  Qin Lyu, Kaushik Chakrabarti, Shobhit Hathi, Souvik Kundu,
  Jianwen Zhang, Zheng Chen. [Hybrid Ranking Network for Text-to-SQL](https://www.microsoft.com/en-us/research/uploads/prod/2020/03/HydraNet_20200311-5e69612887fcb.pdf). 2020 🔥

  `Code`  
  - [https://github.com/naver/sqlova](https://github.com/naver/sqlova)  
  - [https://github.com/xiaojunxu/SQLNet](https://github.com/xiaojunxu/SQLNet)  
  - [https://github.com/guotong1988/NL2SQL-BERT](https://github.com/guotong1988/NL2SQL-BERT)

  `Exe_score`  

  | RoBERTa-Large-HydraNet + EG |92.4|92.2|
  |-|-|-|
  | BERT-Large-HydraNet + EG |92.2|91.8|
  | RoBERTa-Large-HydraNet |89.1|89.2|
  | BERT-Large-HydraNet |88.9 | 88.6 |
  | BERT-XSQL-Attention + EG |92.3|91.8|
  | (Tong) BERT-base-TableContent-used + EG| 91.1 | 90.1 |
  | (Tong) BERT-base-TableContent-used| 90.3 | 89.2 |
  | BERT-XSQL-Attention | 89.5 | 88.7 |
  | BERT-SQLova-LSTM|87.2 |  86.2  |
  |BERT-SQLova-LSTM + EG | 90.2 | 89.6 |
  |GloVe-SQLNet-BiLSTM|69.8 |  68.0  |

---
---

- **`Schema aware Denoising (SeaD)`**  🔥🔥
  > 在text-to-SQL任务中，由于架构设计的限制，seq2seq模型通常会导致局部最优。在本文中，作者提出了一种简单而有效的方法：采用基于transformer的seq2seq模型来加强文本到SQL生成。使用模式感知去噪（SeaD）对seq2seq模型进行训练：由两个去噪目标组成，训练模型从erosion和随机噪声中恢复输入或预测输出(自回归方式)，而不是对encoder施加约束或将任务重新格式化为槽位填充。这些去噪目标作为辅助任务，用于在seq2seq生成中更好地建模结构数据。此外，作者改进并提出了一种子句敏感执行引导（Execution Guided, EG）解码策略，以克服生成模型EG解码的局限性。

  `Paper`
  - [ ] [1] Xuan K ,  Wang Y ,  Wang Y , et al. [SeaD: End-to-end Text-to-SQL Generation with Schema-aware Denoising
](https://arxiv.org/pdf/2105.07911.pdf)[J].  2021.

  `Exe_score`  

  | SeaD + EG |92.9|93.0|
  |-|-|-|
  | SeaD |90.2|90.1|

---
---

- **`Schema Dependency Guided`**  🔥🔥
  > 结合Question和Schema之间的依存关系来进行多任务学习。

  `Paper`
  - [ ] Hui B, Shi X, Geng R, et al. [Improving Text-to-SQL with Schema Dependency Learning](https://arxiv.org/pdf/2103.04399.pdf)[J]. arXiv preprint arXiv:2103.04399, 2021.

  `Exe_score`  

  | SDSQL + EG |92.5|92.4|
  |-|-|-|
  | SDSQL |88.7|88.8|

---
---

- **`BRIDGE^`**   🔥

  `Paper`
  - [ ] Lin X V, Socher R, Xiong C. [Bridging Textual and Tabular Data for Cross-Domain Text-to-SQL Semantic Parsing](https://www.aclweb.org/anthology/2020.findings-emnlp.438.pdf)[C]//EMNLP: Findings. 2020: 4870-4888.

  `Code` 
  - [https://github.com/salesforce/TabularSemanticParsing](https://github.com/salesforce/TabularSemanticParsing)
  - [https://github.com/WING-NUS/slsql](https://github.com/WING-NUS/slsql)

  `Exe_score`  

  | BRIDGE^ + EG |92.6|91.9|
  |-|-|-|
  | BRIDGE |91.7|91.1|

---
---

- **`T5 SeqGenSQL`**  🔥🔥
  > 利用T5预训练语言（文本生成）模型, 将问题直接转换为SQL语句。同时，探索了如何利用表格模式信息对问题进行扩充，生成新的(silver)训练数据集

  `Paper`
  - [ ] Li N ,  Keller B ,  Butler M , et al. [SeqGenSQL -- A Robust Sequence Generation Model for Structured Query Language](https://arxiv.org/pdf/2011.03836.pdf)[J].  2020.
  - [ ] Youssef M, Abdelkader R, et al.[
SQL Generation from Natural Language: A Sequence-to-Sequence Model Powered by the Transformers Architecture and Association Rules](https://pdfs.semanticscholar.org/b877/233410484b2ff2add278105c53b6633d9d20.pdf)[J]. 2021

  `Exe_score`  

  |SeqGenSQL + EG |90.8|90.5|
  |-|-|-|
  |SeqGenSQL(T5-base + 250K silver data) |90.6|90.3|
  |T5-large&mT5-large + Association Rules *| 91.2 | 91.0 |

---
---

- **`Information Extraction Approach`**  
  > 信息抽取的方法: 采用统一的基于BERT的抽取模型来识别query提及的槽位类型，包括序列标注方法、关系抽取和基于文本匹配的链接方法。

  `Paper`
  - [ ] Ping An Life, AI Team. [IE-SQL: Mention Extraction and Linking for SQL Query Generation](https://drive.google.com/file/d/1t3xEltqKpYJGYekAhQ5vYFen1ocHJ3sY/view) 2020

  `Exe_score`  

  | BERT-IE-SQL + EG |92.6|92.5|
  |-|-|-|
  | BERT-IE-SQL |88.7|88.8|

---
---

- **`MRC Approach`**  🔥
  > 阅读理解的方法: 与传统槽位填充方法不同的是，该方法将NL2SQL转化为QA问题,通过统一的MRC框架来预测不同的槽位。

  `Paper`
  - [ ] Yan Z, Ma J, Zhang Y, et al. [SQL Generation via Machine Reading Comprehension](https://www.aclweb.org/anthology/2020.coling-main.31.pdf)[C]//Proceedings of the 28th International Conference on Computational Linguistics. 2020: 350-356.
  
  `Code`  
  - [https://github.com/nl2sql/QA-SQL](https://github.com/nl2sql/QA-SQL)  
  
  `Exe_score`

  | BERT-MRC-SQL + STILTs training + AGG enhancement |87.8|87.4|
  |-|-|-|
  | BERT-MRC-SQL + STILTs training |86.2|86.0|
  | BERT-MRC-SQL |85.9|85.9|

---
---

- **`Model Interactive`**  
  > 基于用户交互的语义解析，更偏向于落地实践。在生成sql后，通过自然语句生成来进一步要求用户进行意图澄清，从而对sql进行修正。

  `Blog` 
  - [Facebook提出全新交互式语义分析框架，自然语言生成SQL语句准确率提升10%](https://mp.weixin.qq.com/s/B3Rw-Rqy8b4-HtWPBtEI_w)  

  `Paper`
  - [ ] Yao Z, Su Y, Sun H, et al. [Model-based Interactive Semantic Parsing: A Unified Framework and A Text-to-SQL Case Study](https://arxiv.org/pdf/1910.05389.pdf)[C]. EMNLP-IJCNLP 2019.  

  `Code`
  - [https://github.com/sunlab-osu/MISP](https://github.com/sunlab-osu/MISP)

----
----
#### **`2. Spider:`**  

- **`GNN Encoding Seq2Seq`**  🔥
  > `Schema-GNN:` 利用多表关联信息来建立一个表名、列名为节点，表内、表间关系为边的图。通过GNN方法计算每一个节点(table item)的隐藏状态。在seq2seq模型的encoding阶段，每个query word 向量对每个 table item隐藏向量进行attention计算， 并将attention权重作为每个query word的图表示。在decoding阶段，结合语法规则，如果输出应为table item,则将输出向量与所有table item隐藏向量进行全连接打分，计算其关联程度。

  > `LGESQL: ` 以往的建图方式存在问题：1）忽略了边在拓扑结构中丰富的语义信息 2）无法区分每个节点的局部和非局部的关系。本文方法(Line Graph Enhanced Text-toSQL)在不构建元路径的情况挖掘潜在的关系特征.借助Line Graph，消息可以有效的在连接节点之间以及拓扑有向边上进行传播。在图迭代过程中，局部和非局部关系被显著地集成。同时，还设计了图剪枝的辅助任务，来提高编码器的识别能力。

  > `ShadowGNN: ` 在跨域结构下，传统的语义解析模型难以适应不可见的数据库模式。为了提高稀少且不可见模式的模型泛化能力，我们提出了一种新的架构ShadowGNN，它可以在抽象和语义级别处理schemas。具体地，通过忽略数据库中语义项的名称，抽象schemas利用图映射神经网络来获得question和schema的去符号化表示。在领域无关表示的基础上，利用关系感知转换器进一步提取question和schema之间的逻辑联系。最后，还应用了一个具有上下文无关语法的SQL解码器。

  > `SADGA: ` Structure-Aware Dual Graph Aggregation Network, 设计了一种基于图结构的聚合方法来学习question图和schema图的映射关系。该聚合方法的特征来源于图的全局链接、局部链接以及双图聚合机制。

  > `S²SQL: ` 以往的基于图的编码器，没有很好的建模question的句法结构。本文利用句法解析器来抽取question的信息，并将句法信息注入到question-schema图编码器中。同时还使用了解耦约束来引导不同的边关系嵌入，从而提升网络性能。

  `Paper`
  - [ ] Krishnamurthy J, Dasigi P, Gardner M. [Neural semantic parsing with type constraints for semi-structured tables](https://www.aclweb.org/anthology/D17-1160.pdf)[C]. EMNLP 2017.
  - [ ] Lin K, Bogin B, Neumann M, et al. [Grammar-based Neural Text-to-SQL Generation](https://arxiv.org/pdf/1905.13326.pdf). 2019.
  - [ ] Bogin B, Gardner M, Berant J. [Representing Schema Structure with Graph Neural Networks for Text-to-SQL Parsing](https://arxiv.org/pdf/1905.06241.pdf)[C]. ACL 2019.  
  - [ ] Bogin B, Gardner M, Berant J. [Global Reasoning over Database Structures for Text-to-SQL Parsing](https://arxiv.org/pdf/1908.11214.pdf)[C]. EMNLP-IJCNLP 2019.
  - [ ] Shaw P, Massey P, Chen A, et al. [Generating Logical Forms from Graph Representations of Text and Entities](https://arxiv.org/pdf/1905.08407.pdf)[C]. ACL 2019.
  - [ ] Kelkar A, Relan R, Bhardwaj V, et al. [Bertrand-DR: Improving Text-to-SQL using a Discriminative Re-ranker](https://arxiv.org/pdf/2002.00557.pdf)[J]. arXiv preprint arXiv:2002.00557, 2020. 
  - [ ] Cao R ,  Chen L ,  Chen Z , et al. [LGESQL: Line Graph Enhanced Text-to-SQL Model with Mixed Local and Non-Local Relations](https://arxiv.org/abs/2106.01093)[C]. ACL. 2021.
  - [ ] Chen Z ,  Chen L ,  Zhao Y , et al. [ShadowGNN: Graph Projection Neural Network for Text-to-SQL Parser](https://arxiv.org/pdf/2104.04689.pdf)[C]. NAACL. 2021.
  - [ ] Cai R ,  Yuan J ,  Xu B , et al. SADGA: Structure-Aware Dual Graph Aggregation Network for Text-to-SQL(https://arxiv.org/abs/2111.00653)[C].  NeurIPS 2021.
  - [ ] Hui B ,  Geng R ,  Wang L , et al. [S²SQL: Injecting Syntax to Question-Schema Interaction Graph Encoder for Text-to-SQL Parsers](https://arxiv.org/abs/2203.06958)[C].  ACL Findings. 2022.

  `Code`  
  - [https://github.com/benbogin/spider-schema-gnn](https://github.com/benbogin/spider-schema-gnn)
  - [https://github.com/benbogin/spider-schema-gnn-global](https://github.com/benbogin/spider-schema-gnn-global)
  - [https://github.com/amolk/Bertrand-DR](https://github.com/amolk/Bertrand-DR)
  - [https://github.com/rhythmcao/text2sql-lgesql](https://github.com/rhythmcao/text2sql-lgesql) 
  - [https://github.com/WowCZ/shadowgnn](https://github.com/WowCZ/shadowgnn)
  - [https://github.com/DMIRLAB-Group/SADGA](https://github.com/DMIRLAB-Group/SADGA)
  - 

  `Log_score`

  | S²SQL + ELECTRA (DB content used)|76.4|72.1|
  |:-:|:-:|:-:|
  | SADGA + GAP (DB content used) |73.1 | 70.1|
  | LGESQL + ELECTRA (DB content used) | 75.1| 72.0 |
  | LGESQL + BERT (DB content used | 74.1 | 68.3 |
  | LGESQL + Glove (DB content used)  |67.6|62.8|
  | ShadowGNN + RoBERTa (DB content used) |72.3|66.1|
  | ShadowGNN (DB content used)|-|64.8|
  | GNN + Bertrand-DR | 57.9 | 54.6 |
  | Global-GNN  |52.7|47.4|
  | GNN | 40.7 | 39.4 |
  | GNN w/edge vectors| 32.1 | - |

---
---

- **`RATSQL related works`**  🔥🔥🔥  

  `Paper`  
  - [ ] [1] Wang B, Shin R, Liu X, et al.[RAT-SQL: Relation-Aware Schema Encoding and Linking for Text-to-SQL Parsers ](https://arxiv.org/pdf/1911.04942.pdf)[C]. ACL 2020. 
    <!-- [ICLR 2020](https://openreview.net/forum?id=H1egcgHtvB). -->
  - [ ] [2] Deng X, Awadallah A H, Meek C, et al. [Structure-Grounded Pretraining for Text-to-SQL](https://arxiv.org/pdf/2010.12773.pdf)[C]. NAACL, 2021.
  - [ ] [3] Gan Y ,  Chen X ,  Xie J , et al. [Natural SQL: Making SQL Easier to Infer from Natural Language Specifications](https://arxiv.org/abs/2109.05153)[C]. EMNLP Findings. 2021.
  - [ ] [4] Yu T, Wu C S, Lin X V, et al. [GraPPa: Grammar-Augmented Pre-Training for Table Semantic Parsing](https://arxiv.org/abs/2009.13845)[C]. ICLR 2021.
  - [ ] [5] Shi P ,  Ng P ,  Wang Z , et al. [Learning Contextual Representations for Semantic Parsing with Generation-Augmented Pre-Training](https://arxiv.org/abs/2012.10309)[C]. AAAI 2021.
  - [ ] [6] Zhao L, Cao H, Zhao Y. [GP: Context-free Grammar Pre-training for Text-to-SQL Parsers](https://arxiv.org/pdf/2101.09901.pdf)[J]. arXiv preprint arXiv:2101.09901, 2021.

    
  `Code`
  - [https://github.com/Microsoft/rat-sql](https://github.com/Microsoft/rat-sql)
  - [https://github.com/ygan/NatSQL](https://github.com/ygan/NatSQL)
  - [https://github.com/awslabs/gap-text2sql](https://github.com/awslabs/gap-text2sql)
  - 

  `Exe_score`

  | [3] RATSQL + GAP + NatSQL (DB content used) | 73.3 |
  |:-:|:-:|
  
  `Log_score` 

  | RAT-SQL + GraPPa + Adv (DB content used)|75.5|70.5|
  |:-:|:-:|:-:|
  | RATSQL++ + ELECTRA (DB content used)|75.7|70.3|
  | [6] RATSQL + GraPPa + GP (DB content used)|72.8|69.8|
  | [5] RATSQL + GAP (DB content used) |71.8|69.7|
  | [4] RATSQL + GraPPa (DB content used) |73.4|69.6|
  | [3] RATSQL + GAP + NatSQL (DB content used) | - | 68.7 |
  | [2] RAT-SQL + STRUG (DB content used) | 72.6 |68.4|
  | [1] RATSQL v3 + BERT (DB content used) |69.7|65.6|
  | [1] RATSQL v2 + BERT (DB content used) | 65.8 | 61.9 |
  | [1] RATSQL v2 (DB content used)| 62.7| 57.2|
  | [1] RATSQL + BERT | 60.8 | 55.7 |
  | [1] RATSQL  |60.6|53.7|

----
----

- **`MSRA: IRNet related works`**  🔥🔥  

  `Blog & Video`  
  - [智能数据分析技术，解锁Excel“对话”新功能 Conversational Data Analysis](https://www.msra.cn/zh-cn/news/features/conversational-data-analysis)
  - [Use Ideas in Excel to get Immediate answers with ONE Click]( https://www.youtube.com/watch?v=bey_1SUTB4k)

  `Paper`  
  - [ ] Guo J, Zhan Z, Gao Y, et al. [Towards Complex Text-to-SQL in Cross-Domain Database with Intermediate Representation](https://arxiv.org/pdf/1905.08205.pdf)[C]. ACL 2019.
  - [ ] Dong Z, Sun S, Liu H, et al. [Data-Anonymous Encoding for Text-to-SQL Generation](https://www.aclweb.org/anthology/D19-1543.pdf)[C] EMNLP-IJCNLP 2019.
  - [ ] Liu H, Fang L, Liu Q, et al. [Leveraging Adjective-Noun Phrasing Knowledge for Comparison Relation Prediction in Text-to-SQL](https://www.aclweb.org/anthology/D19-1356.pdf)[C]. EMNLP-IJCNLP 2019.
  - [ ] Liu Q, Chen B, Lou J G, et al. [FANDA: A Novel Approach to Perform Follow-up Query Analysis](https://arxiv.org/pdf/1901.08259.pdf)[C]. AAAI 2019.
  - [ ] Liu Q, Chen B, Liu H, et al. [A Split-and-Recombine Approach for Follow-up Query Analysis](https://www.aclweb.org/anthology/D19-1535.pdf)[C]. EMNLP-IJCNLP 2019.

    
  `Code`
  - [https://github.com/microsoft/IRNet](https://github.com/microsoft/IRNet)
  - [https://github.com/neeraj-bhat/IRNet/tree/dev](https://github.com/neeraj-bhat/IRNet/tree/dev)

  
  `Log_score` 

  | IRNet++ + XLNet (DB content used) |65.5|60.1|
  |:-:|:-:|:-:|
  | IRNet++ + XLNet (DB content used) |65.5|60.1|
  | IRNet-v2 + BERT  |63.9|55.0|
  | IRNet + BERT-Base | 61.9 | 54.7 |
  | IRNet-v2 | 55.4 | 48.5 |
  | IRNet| 53.2 | 46.7 | 

-------
-------
- **`MSRA DKI Group's works`**  🔥🔥  

  `Paper & Code`
  - [https://github.com/microsoft/ContextualSP](https://github.com/microsoft/ContextualSP)

  `Log_score` 

  | ETA + BERT (DB content used) |70.8|65.3|
  |:-:|:-:|:-:|

-----
-----
- **`PICARD`**

  `Paper`
  - [ ] Scholak T ,  Schucher N ,  Bahdanau D . [PICARD: Parsing Incrementally for Constrained Auto-Regressive Decoding from Language Models](https://arxiv.org/abs/2109.05093)[C].  EMNLP. 2021.

  `Code`
  - [https://github.com/ElementAI/picard](https://github.com/ElementAI/picard)

  `Log_score`  

  | PICARD + T5-3B (DB content used)|75.5|71.9|
  |:-:|:-:|:-:|

  `Exe_score` 
  | PICARD + T5-3B (DB content used)| - | 75.1 |
  |:-:|:-:|:-:|

-----
-----
- **`DT-Fixup SQL-SP`**

  `Paper`
  - [ ] Xu P ,  Kumar D ,  Yang W , et al. [Optimizing Deeper Transformers on Small Datasets](https://arxiv.org/abs/2012.15355)[C]. ACL. 2021.

  `Code`
  - [https://github.com/BorealisAI/DT-Fixup](https://github.com/BorealisAI/DT-Fixup)

  `Log_score`  

  | DT-Fixup SQL-SP + RoBERTa (DB content used)|75.0|70.9|
  |:-:|:-:|:-:|

-----
-----
- **`RaSaP`**

  `Paper`
  - [ ] Hua Ng  J ,  Wa Ng  Y ,  Wa Ng  Y , et al. [Relation Aware Semi-autoregressive Semantic Parsing for NL2SQL](https://arxiv.org/abs/2108.00804)[J].  2021.

  `Log_score`  

  | RaSaP + ELECTRA (DB content used) |74.7|69.0|
  |:-:|:-:|:-:|


------
------

- **`EditSQL`**

  `Paper`
  - [ ] Zhang R, Yu T, Er H Y, et al. [Editing-Based SQL Query Generation for Cross-Domain Context-Dependent Questions](https://arxiv.org/pdf/1909.00786.pdf)[C]. EMNLP-IJCNLP 2019.

  `Code`
  - [https://github.com/ryanzhumich/editsql](https://github.com/ryanzhumich/editsql)

  `Log_score`  

  | EditSQL + BERT  |57.6|53.4|
  |:-:|:-:|:-:|
  | EditSQL | 36.4 | 32.9 |  

----
----

- **`RYANSQL`**

  `Paper`
  - [ ] Choi D H, Shin M C, Kim E G, et al. [RYANSQL: Recursively Applying Sketch-based Slot Fillings for Complex Text-to-SQL in Cross-Domain Databases]([RYANSQL: Recursively Applying Sketch-based Slot Fillings for Complex Text-to-SQL in Cross-Domain Databases](https://arxiv.org/pdf/2004.03125.pdf))[J]. 2020.

  `Log_score`  
  | RYANSQL v2 + BERT  | 70.6 | 60.6 |
  |:-:|:-:|:-:|
  | RYANSQL + BERT | 66.6 | 58.2 | 
  | RYANSQL  | 43.3 | - |

----
----

- **`SmBoP`**   
  > 与自上而下的自回归分析相比，半自回归自底向上解析器具有多种优势。首先，由于每个解码步骤中的子树都是并行生成的，因此理论上的运行时间是对数而不是线性复杂度。其次，自下而上的方法学习在每个步骤上学习语义子程序的表示，而不是语义上模糊的部分树。最后，SMBOP基于Transformer的层将子树相互关联起来，与传统的beam-search不同，以探索过的其他树木为条件为树进行评分。

  `Paper`
  - [ ] Rubin O, Berant J. [SmBoP: Semi-autoregressive Bottom-up Semantic Parsing](https://arxiv.org/pdf/2010.12412.pdf)[C]. NAACL, 2021.  

  `Code`  
  [https://github.com/OhadRubin/SmBop](https://github.com/OhadRubin/SmBop)

  `Log_score`  

  | SmBoP + GraPPa (DB content used) |74.7 | 69.5|
  |:-:|:-:|:-:|
  | SmBoP + BART | 66.0 | 60.5 |

  `Exe_score` 
  | SmBoP + GraPPa (DB content used) | - | 71.1 |
  |:-:|:-:|:-:|

----
----

- **`SLSQL`**   
  > Schema Linking is the crux for the current text-to-SQL task. 

  `Paper`
  - [ ] Lei W, Wang W, Ma Z, et al. [Re-examining the Role of Schema Linking in Text-to-SQL](https://www.aclweb.org/anthology/2020.emnlp-main.564.pdf)[C]. EMNLP 2020: 6943-6954.

  `Code` 
  - [https://github.com/salesforce/TabularSemanticParsing](https://github.com/salesforce/TabularSemanticParsing)
  - [https://github.com/WING-NUS/slsql](https://github.com/WING-NUS/slsql)

  `Log_score`  

  | SLSQL + BERT + Data Annotation | 60.8 | 55.7 |
  |:-:|:-:|:-:|

----
----

- **`BRIDGE `** 
  > 

  `Paper`
  - [ ] Lin X V, Socher R, Xiong C. [Bridging Textual and Tabular Data for Cross-Domain Text-to-SQL Semantic Parsing](https://www.aclweb.org/anthology/2020.findings-emnlp.438.pdf)[C]//EMNLP: Findings. 2020: 4870-4888.

  `Code` 
  - [https://github.com/salesforce/TabularSemanticParsing](https://github.com/salesforce/TabularSemanticParsing)
  - [https://github.com/WING-NUS/slsql](https://github.com/WING-NUS/slsql)


  `Log_score`  

  | BRIDGE(k = 2) + BERT (DB content used) | 65.5 | 59.2 |
  |:-:|:-:|:-:|
  | BRIDGE(k = 1) + BERT (DB content used) | 65.3 | - |

  `Exe_score` 
  | BRIDGE v2 + BERT(ensemble) (DB content used) | - | 68.3 |
  |:-:|:-:|:-:|
  | BRIDGE v2 + BERT (DB content used) | - | 64.3 |
  | BRIDGE(k = 2) + BERT (DB content used) | - | 59.9 |
----
----

- **`GAZP `** 
  > GAZP combines a forward semantic parser with a backward utterance generator to synthesize data (e.g. utterances and SQL queries)
  in the new environment, then selects cycleconsistent examples to adapt the parser. Unlike data-augmentation, which typically synthesizes unverified examples in the training environment, GAZP synthesizes examples in the new environment whose inputoutput consistency are verified.

  `Paper`
  - [ ] Zhong V, Lewis M, Wang S I, et al. [Grounded adaptation for zero-shot executable semantic parsing](https://arxiv.org/pdf/2009.07396.pdf)[C]. EMNLP-2020.


  `Exe_score` 
  | GAZP + BERT | - | 53.5 |
  |:-:|:-:|:-:|

----
----

- **`SQLNet Framework`**  

  `Paper`
  - [ ] [Leveraging Adjective-Noun Phrasing Knowledge for Comparison Relation Prediction in Text-to-SQL](https://www.aclweb.org/anthology/D19-1356.pdf)[C]. EMNLP 2019
  - [ ] Yu T, Yasunaga M, Yang K, et al. [Syntaxsqlnet: Syntax tree networks for complex and cross-domaintext-to-sql task](https://arxiv.org/pdf/1810.05237.pdf)[C]. EMNLP 2018.
  - [ ] Dongjun Lee. [Clause-Wise and Recursive Decoding for Complex and Cross-Domain Text-to-SQL Generation](https://arxiv.org/pdf/1904.08835.pdf)[C]. EMNLP 2019.
  - [ ] Lin K, Bogin B, Neumann M, et al. [Grammar-based Neural Text-to-SQL Generation](https://arxiv.org/pdf/1905.13326.pdf). 2019.

  `Code`  
  - [https://github.com/taoyds/syntaxSQL](https://github.com/taoyds/syntaxSQL)

  `Score`  

  | GrammarSQL | 34.8 | 33.8 |
  |:-:|:-:|:-:|
  | SyntaxSQLNet + augment  |24.8|27.2|
  | RCSQL | 28.5 | 24.3 | 
  | SyntaxSQLNet | 18.9 | 19.7 |
  | SQLNet | 10.9 | 12.4 |

---
---

#### **`3. UnifiedSKG:`**  🔥🔥


`Blog`  
 - [ ] [结构化知识的统一建模和多任务学习](https://mp.weixin.qq.com/s/ddhZoOHa2eWKZoHESIiK3Q)

`Code`  
 - [ ] [https://github.com/hkunlp/unifiedskg](https://github.com/hkunlp/unifiedskg)

`Paper`

 - [ ] Xie T ,  Wu C H ,  Shi P , et al. [UnifiedSKG: Unifying and Multi-Tasking Structured Knowledge Grounding with Text-to-Text Language Models](https://arxiv.org/abs/2201.05966)[J]. arXiv e-prints, 2022.


#### 三、相关资源扩展 (extend resources)
##### 1. Related Works  
##### 1.1 `Pre-training`  🔥🔥🔥 
  > jointly learns representations of natural language utterances and table schemas by leveraging generation models to generate pre-train data.
  - [ ] Shi P ,  Ng P ,  Wang Z , et al. [GAP: Learning Contextual Representations for Semantic Parsing with Generation-Augmented Pre-Training](https://arxiv.org/abs/2012.10309)[C]. AAAI 2021.
  
  >  A novel weakly supervised Structure-Grounded pretraining framework (STRUG) for text-to-SQL that can effectively learn to capture text-table alignment based on a parallel text-table corpus. 
  - [ ]Deng X, Awadallah A H, Meek C, et al. [Structure-Grounded Pretraining for Text-to-SQL](https://arxiv.org/pdf/2010.12773.pdf)[C]. NAACL, 2021.

  >  A new method for Text-to-SQL parsing, Grammar Pre-training (GP),is proposed to decode deep relations between question and database.
  - [ ]Zhao L, Cao H, Zhao Y. [GP: Context-free Grammar Pre-training for Text-to-SQL Parsers](https://arxiv.org/pdf/2101.09901.pdf)[J]. arXiv preprint arXiv:2101.09901, 2021.

  >  An effective pre-training approach for table semantic parsing that learns a compositional inductive bias in the joint representations of textual and tabular data.
  - [ ] Yu T, Wu C S, Lin X V, et al. [GraPPa: Grammar-Augmented Pre-Training for Table Semantic Parsing](https://arxiv.org/abs/2009.13845)[C]. ICLR 2021.
  
  > this paper designs two novel pre-training objectives to impose the desired inductive bias into the learned representations for table pre-training. 
  - [ ] Qin B ,  Wang L ,  Hui B , et al. [SDCUP: Schema Dependency-Enhanced Curriculum Pre-Training for Table Semantic Parsing](https://arxiv.org/abs/2111.09486)[J]. 2021.

  > table pre-training can be realized by learning a neural SQL executor over a synthetic corpus, which is obtained by automatically synthesizing executable SQL queries. 
  - [ ] Liu Q ,  Chen B ,  Guo J , et al. [TAPEX: Table Pre-training via Learning a Neural SQL Executor(https://arxiv.org/abs/2107.07653)[J].  2021.
  
  > A pretrained language model that jointly learns representations for NL sentences and (semi-)structured tables.
  - [ ] Pengcheng Yin, Graham Neubig, et al. [TaBERT: Pretraining for Joint Understanding of Textual and Tabular Data](https://arxiv.org/abs/2005.08314)[C]. ACL 2020. 
  
  > this paper designs two novel pre-training objectives to impose the desired inductive bias into the learned representations for table pre-training. 
  - [ ] Bowen Q, LiHan W, et al.[Linking-Enhanced Pre-Training for Table Semantic Parsing](https://arxiv.org/abs/2111.09486). 2021

  > Adapting a semantic parser trained on a single language.
  - [ ] Tom Sherborne, Yumo Xu, Mirella Lapata. [Bootstrapping a Crosslingual Semantic Parser](https://arxiv.org/abs/2004.02585).2020.

##### 1.2 `Systems`
  - [ ] Zeng J, Lin X V, Xiong C, et al. [Photon: A Robust Cross-Domain Text-to-SQL System](https://arxiv.org/pdf/2007.15280.pdf)[J]. 2020.
  - [ ] Brunner U, Stockinger K. [ValueNet: A Neural Text-to-SQL Architecture Incorporating Values](https://arxiv.org/pdf/2006.00888.pdf)[J]. 2020.
  - [ ] Elgohary A, Hosseini S, Awadallah A H. [Speak to your Parser: Interactive Text-to-SQL with Natural Language Feedback](https://arxiv.org/pdf/2006.00888)[J]. 2020.

##### 1.3 `Surveys`
  - [ ] Jovan, Martina, Frosina. [Recent Advances in SQL Query Generation: A Survey](https://arxiv.org/pdf/2005.07667.pdf)//Part of the 17th International Conference on Informatics and Information Technologies. Received best paper award. 2020.

##### 1.4 `Blogs`
  - [ ] [NL2SQL概述：一文了解NL2SQL](https://www.csuldw.com/2019/10/20/2019-10-20-nl2sql-introduction/)  
  - [ ] [哈工大SCIR: 一文了解Text-to-SQL](https://mp.weixin.qq.com/s/ucFtWopoErtUCYDTLv2kFg)
  - [ ] [表格问答1：简介-朴素人工智能](https://mp.weixin.qq.com/s/iIoy9cIitlaH1p_msrbYoQ) 
  - [ ] [表格问答2：模型](https://mp.weixin.qq.com/s/aXXhR4u-AvJY-h8595RJew) 
  - [ ] [表格问答完结篇：落地应用](https://mp.weixin.qq.com/s/0uEXOTfbEq86oIVnMrogRA)
  - [ ] [ACL2020 表格预训练工作速览](https://mp.weixin.qq.com/s/AF-Wt5lKW2-oWBgdcCyWXA)

##### 1.5 `Other Papers`
  - [ ] Dhamdhere K, McCurley K S, Nahmias R, et al. [Analyza: Exploring data with conversation](https://dl.acm.org/citation.cfm?id=3025227)[C]//Proceedings of the 22nd International Conference on Intelligent User Interfaces. ACM, 2017.
  - [ ] Chen S, San A, Liu X, et al. [A Tale of Two Linkings: Dynamically Gating between Schema Linking and Structural Linking for Text-to-SQL Parsing](https://arxiv.org/abs/2009.14809)[C]. COLING 2020.
  -  Dou L ,  Gao Y ,  Pan M , et al. [UniSAr: A Unified Structure-Aware Autoregressive Language Model for Text-to-SQL](https://arxiv.org/abs/2203.07781)[J].  2022.

##### 1.6 `Tools`
  -  Test suite for text2sql code: [https://github.com/taoyds/test-suite-sql-eval](https://github.com/taoyds/test-suite-sql-eval)   
  -  Test suite for text2sql paper: Zhong R, Yu T, Klein D. [Semantic Evaluation for Text-to-SQL with Distilled Test Suites](https://arxiv.org/pdf/2010.02840.pdf)[C]. EMNLP2020.
  -  SQL Parser [https://github.com/mozilla/moz-sql-parser](https://github.com/mozilla/moz-sql-parser)

##### 2. SQL2Seq  

`Paper`  
- [ ] Xu K, Wu L, Wang Z, et al. [Graph2seq: Graph to sequence learning with attention-based neural networks](https://arxiv.org/pdf/1804.00823.pdf).2018. 
- [ ] Xu K, Wu L, Wang Z, et al. [SQL-to-text generation with graph-to-sequence model](https://arxiv.org/pdf/1809.05255.pdf)[C]. EMNLP 2018.

`Code`  
- [https://github.com/IBM/SQL-to-Text](https://github.com/IBM/SQL-to-Text)
- [https://github.com/IBM/Graph2Seq](https://github.com/IBM/Graph2Seq)
- [https://github.com/RandolphVI/Graph2Seq](https://github.com/RandolphVI/Graph2Seq)   

##### 3. 图神经网络（GNN)  

`Paper`  
- [https://github.com/thunlp/GNNPapers](https://github.com/thunlp/GNNPapers)
- [https://github.com/IndexFziQ/GNN4NLP-Papers](https://github.com/IndexFziQ/GNN4NLP-Papers)
- [https://github.com/nnzhan/Awesome-Graph-Neural-Networks](https://github.com/nnzhan/Awesome-Graph-Neural-Networks)
- [https://github.com/naganandy/graph-based-deep-learning-literature](https://github.com/naganandy/graph-based-deep-learning-literature)
- [https://github.com/svjan5/GNNs-for-NLP](https://github.com/svjan5/GNNs-for-NLP)

`Code`  
- [https://github.com/rusty1s/pytorch_geometric](https://github.com/rusty1s/pytorch_geometric)
- [https://github.com/dmlc/dgl](https://github.com/dmlc/dgl)
- [https://github.com/tkipf/pygcn](https://github.com/tkipf/pygcn)
- [https://github.com/chingyaoc/ggnn.pytorch](https://github.com/chingyaoc/ggnn.pytorch)
- [https://github.com/bdqnghi/ggnn.tensorflow](https://github.com/bdqnghi/ggnn.tensorflow)


