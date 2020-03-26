## NL2LF 
___(持续更新中...)___
> The Resources for "Natural Language to Logical Form" Research;  
> "自然语言转逻辑形式"研究资料收集: 
> 本阶段主要以**NL2SQL**的研究为主, 主要包括评测公开数据集、相关论文和部分代码实现、相关博客或公众号文章。

[NL2SQL](#nl2sql--text2sql)  
[一、主要评测数据集 dataset](#一主要评测数据集dataset)  
[二、主要论文方法及代码实现 papers&code](#二主要论文方法及代码实现paperscode)  
&nbsp;&nbsp;&nbsp;&nbsp;[1. WikiSQL](#1-wikisql)  
&nbsp;&nbsp;&nbsp;&nbsp;[2. Spider](#2-spider)  
[三、相关资源扩展 extend-resources](#三相关资源扩展-extend-resources)  
&nbsp;&nbsp;&nbsp;&nbsp;[1. RelatedWorks](#1-relatedworks)  
&nbsp;&nbsp;&nbsp;&nbsp;[2. SQL2Seq](#1-sql2seq)  
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

---
- **DuSQL** 
  > 百度2020语言与智能技术竞赛：语义解析任务，大规模开放领域的复杂中文Text-to-SQL数据集
  > 数据特点：
  > 1. 包含200个Database以及对应的2.3万对(question, SQL query)，其中18000对用于训练集，2000用于验证集，3000用于测试集。
  > 2. 200个Database来自百科infobox、百科表格数据、以及互联网上存在的表格数据。每个Database包含若干张表格（2-11张，平均4.1张），人工构建了表之间的链接操作（即foreign key）。为了验证解析算法Database无关性及question无关性，在训练集合和测试集合的Database无交叉。
  >  从发布的样例集看，相比较spider，不含有join操作。因此主要是复杂的单表查询，涉及groupby，order， limit 以及集合交并差操作。
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
  **比赛时间：2020/03/10 - 2020/05/20**

#### 二、主要论文方法及代码实现（Papers&Code）
> 论文主要以WikiSQL和Spider为评测数据，相应排行榜详见任务主页。  
> 下面主要整理具有代表性的方法，持续更新补充...  
> 注: 
> score表示 | model | Dev accuracy |  Test accuracy  |，WikiSQL表示执行准确率，Spider表示逻辑准确率，且不包括值预测。

#### **`1. WikiSQL:`** 
**`Weakly Supervised`**  
> 采用弱监督方法，即不使用sql的逻辑形式作为监督信号。 

`Paper`
- [ ] Min S, Chen D, Hajishirzi H, et al. [A discrete hard em approach for weakly supervised question answering](https://www.cs.princeton.edu/~danqic/papers/emnlp2019.pdf)[C]. EMNLP-IJCNLP 2019.  
- [ ] Agarwal R, Liang C, Schuurmans D, et al. [Learning to Generalize from Sparse and Underspecified Rewards](https://arxiv.org/pdf/1902.07198.pdf). 2019.  
- [ ] Liang C, Norouzi M, Berant J, et al. [Memory augmented policy optimization for program synthesis and semantic parsing](https://papers.nips.cc/paper/8204-memory-augmented-policy-optimization-for-program-synthesis-and-semantic-parsing.pdf)[C].NeurIPS, 2018: 9994-10006.


`Code` 
- [https://github.com/shmsw25/qa-hard-em](https://github.com/shmsw25/qa-hard-em)  
- [https://github.com/google-research/google-research/tree/master/meta_reward_learning](https://github.com/google-research/google-research/tree/master/meta_reward_learning)

`Score`  

|Hard-EM|84.4 |  83.9  |
|-|-|-|
|MeRL | 74.9 | 74.8 |
|MAPO | 72.2 | 72.1 |

---
**`ExecutionGuided`**  
> Execution Guided 可以在解码阶段通过执行错误对生成sql的项进行修正,从而过滤了一些不符合实际的sql语句。主要分为三类执行错误：1）句法解析错误，即生成的sql语法错误。2）执行失败。常见的run-time error, 例如SUM( ) 和比较string类型的数据；3）假设执行结果不为空，则空查询的条件错误。例如条件值实际并不存在于预测的列中, 因此会去 Beam Search 实际包含条件值的列。

`Paper`  
- [ ]  Wang C, Huang P S, Polozov A, et al. [Robust Text-to-SQL Generation with Execution-Guided Decoding](https://arxiv.org/pdf/1807.03100.pdf)[J]. 2018.  
- [ ]  Wang C, Brockschmidt M, Singh R. [Pointing out SQL queries from text](https://openreview.net/pdf?id=BkUDW_lCb)[J]. 2018. 
- [ ]  Dong L, Lapata M. [Coarse-to-fine decoding for neural semantic parsing](https://arxiv.org/pdf/1805.04793.pdf)[J]. 2018.
- [ ]  Huang P S, Wang C, Singh R, et al. [Natural language to structured query generation via meta-learning](https://arxiv.org/pdf/1803.02400.pdf)[J]. 2018.


`Code`  
- [https://github.com/microsoft/PointerSQL](https://github.com/microsoft/PointerSQL)  
- [https://github.com/donglixp/coarse2fine](https://github.com/donglixp/coarse2fine)  

`Score`  

|Coarse2Fine + EG| 84.0 | 83.8 |
|-|-|-|
| Coarse2Fine | 79.0 | 78.5 |
| Pointer-SQL + EG | 78.4 |  78.3  |
| Pointer-SQL | 72.5 | 71.9 |

---
**`SQLNet Framework`**  
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
- [ ]  He P, Mao Y, Chakrabarti K, et al. [X-SQL: reinforce schema representation with context](https://arxiv.org/pdf/1908.08113.pdf)[J]. 2019.
- [ ]  Tong Guo, Huilin Gao. [Content Enhanced BERT-based Text-to-SQL Generation ](https://arxiv.org/pdf/1910.07179.pdf).2019.

`Code`  
- [https://github.com/naver/sqlova](https://github.com/naver/sqlova)  
- [https://github.com/xiaojunxu/SQLNet](https://github.com/xiaojunxu/SQLNet)  
- [https://github.com/guotong1988/NL2SQL-BERT](https://github.com/guotong1988/NL2SQL-BERT)

`Score`  

| BERT-XSQL-Attention + EG |92.3|91.8|
|-|-|-|
| BERT-XSQL-Attention | 89.5 | 88.7 |
| BERT-SQLova-LSTM|87.2 |  86.2  |
|BERT-SQLova-LSTM + EG | 90.2 | 89.6 |
|GloVe-SQLNet-BiLSTM|69.8 |  68.0  |

---
**`Model Interactive`**  
> 基于用户交互的语义解析，更偏向于落地实践。在生成sql后，通过自然语句生成来进一步要求用户进行意图澄清，从而对sql进行修正。

`Blog` 
- [Facebook提出全新交互式语义分析框架，自然语言生成SQL语句准确率提升10%](https://mp.weixin.qq.com/s/B3Rw-Rqy8b4-HtWPBtEI_w)  

`Paper`
- [ ] Yao Z, Su Y, Sun H, et al. [Model-based Interactive Semantic Parsing: A Unified Framework and A Text-to-SQL Case Study](https://arxiv.org/pdf/1910.05389.pdf)[C]. EMNLP-IJCNLP 2019.  

`Code`
- [https://github.com/sunlab-osu/MISP](https://github.com/sunlab-osu/MISP)

----
#### **`2. Spider:`**  

**`GNN Encoding Seq2Seq`**  
> 利用多表关联信息来建立一个表名、列名为节点，表内、表间关系为边的图。
> 通过GNN方法计算每一个节点(table item)的隐藏状态。
> 在seq2seq模型的encoding阶段，每个query word 向量对每个 table item隐藏向量进行attention计算， 并将attention权重作为每个query word的图表示。
> 在decoding阶段，结合语法规则，如果输出应为table item,则将输出向量与所有table item隐藏向量进行全连接打分，计算其关联程度。

`Paper`
- [ ] Krishnamurthy J, Dasigi P, Gardner M. [Neural semantic parsing with type constraints for semi-structured tables](https://www.aclweb.org/anthology/D17-1160.pdf)[C]. EMNLP 2017.
- [ ] Lin K, Bogin B, Neumann M, et al. [Grammar-based Neural Text-to-SQL Generation](https://arxiv.org/pdf/1905.13326.pdf). 2019.
- [ ] Bogin B, Gardner M, Berant J. [Representing Schema Structure with Graph Neural Networks for Text-to-SQL Parsing](https://arxiv.org/pdf/1905.06241.pdf)[C]. ACL 2019.  
- [ ] Bogin B, Gardner M, Berant J. [Global Reasoning over Database Structures for Text-to-SQL Parsing](https://arxiv.org/pdf/1908.11214.pdf)[C]. EMNLP-IJCNLP 2019.
- [ ] Shaw P, Massey P, Chen A, et al. [Generating Logical Forms from Graph Representations of Text and Entities](https://arxiv.org/pdf/1905.08407.pdf)[C]. ACL 2019.

`Code`  
- [https://github.com/benbogin/spider-schema-gnn](https://github.com/benbogin/spider-schema-gnn)
- [https://github.com/benbogin/spider-schema-gnn-global](https://github.com/benbogin/spider-schema-gnn-global)

`Score`

| BERTRAND + GNN | 57.9 | 54.6 |
|:-:|:-:|:-:|
| Global-GNN  |52.7|47.4|
| GNN | 40.7 | 39.4 |
| GNN w/edge vectors| 32.1 | - |

---
**`RATSQL`**  

`Paper`
- [ ] Wang B, Shin R, Liu X, et al.[RAT-SQL: Relation-Aware Schema Encoding and Linking for Text-to-SQL Parsers ](https://arxiv.org/pdf/1911.04942.pdf)[C].  
  [ICLR 2020](https://openreview.net/forum?id=H1egcgHtvB). 
  [review on ACL 2020]().


`Score`  

| RATSQL v2 + BERT (DB content used) | 65.8 | 61.9 |
|:-:|:-:|:-:|
| RASQL + BERT | 60.8 | 55.7 |
| RAT-SQL  |60.6|53.7|

---
**`IRNet`**  **`MSRA work`**  
`Blog`  
- [智能数据分析技术，解锁Excel“对话”新功能 Conversational Data Analysis](https://www.msra.cn/zh-cn/news/features/conversational-data-analysis)

`Paper`  
- [ ] Guo J, Zhan Z, Gao Y, et al. [Towards Complex Text-to-SQL in Cross-Domain Database with Intermediate Representation](https://arxiv.org/pdf/1905.08205.pdf)[C]. ACL 2019.
- [ ] Dong Z, Sun S, Liu H, et al. [Data-Anonymous Encoding for Text-to-SQL Generation](https://www.aclweb.org/anthology/D19-1543.pdf)[C] EMNLP-IJCNLP 2019.
- [ ] Liu H, Fang L, Liu Q, et al. [Leveraging Adjective-Noun Phrasing Knowledge for Comparison Relation Prediction in Text-to-SQL](https://www.aclweb.org/anthology/D19-1356.pdf)[C]. EMNLP-IJCNLP 2019.
- [ ] Liu Q, Chen B, Lou J G, et al. [FANDA: A Novel Approach to Perform Follow-up Query Analysis](https://arxiv.org/pdf/1901.08259.pdf)[C]. AAAI 2019.
- [ ] Liu Q, Chen B, Liu H, et al. [A Split-and-Recombine Approach for Follow-up Query Analysis](https://www.aclweb.org/anthology/D19-1535.pdf)[C]. EMNLP-IJCNLP 2019.

  
`Code`
- [https://github.com/neeraj-bhat/IRNet/tree/dev](https://github.com/neeraj-bhat/IRNet/tree/dev)

`Score`  

| IRNet-v2 + BERT  |63.9|55.0|
|:-:|:-:|:-:|
| IRNet + BERT-Base | 61.9 | 54.7 |
| IRNet-v2 | 55.4 | 48.5 |
| IRNet| 53.2 | 46.7 | 

---
**`EditSQL`**  

`Paper`
- [ ] Zhang R, Yu T, Er H Y, et al. [Editing-Based SQL Query Generation for Cross-Domain Context-Dependent Questions](https://arxiv.org/pdf/1909.00786.pdf)[C]. EMNLP-IJCNLP 2019.

`Code`
- [https://github.com/ryanzhumich/editsql](https://github.com/ryanzhumich/editsql)

`Score`  

| EditSQL + BERT  |57.6|53.4|
|:-:|:-:|:-:|
| EditSQL | 36.4 | 32.9 |  

----
**`SQLNet Framework`**  

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
#### 三、相关资源扩展 (extend resources)
##### 1. RelatedWorks  

`Blog`
- [ ] [NL2SQL概述：一文了解NL2SQL](https://www.csuldw.com/2019/10/20/2019-10-20-nl2sql-introduction/)  
- [ ] [哈工大SCIR: 一文了解Text-to-SQL](https://mp.weixin.qq.com/s/ucFtWopoErtUCYDTLv2kFg)

`Paper`
- [ ] Dhamdhere K, McCurley K S, Nahmias R, et al. [Analyza: Exploring data with conversation](https://dl.acm.org/citation.cfm?id=3025227)[C]//Proceedings of the 22nd International Conference on Intelligent User Interfaces. ACM, 2017.

##### 2. SQL2Seq  

`Paper`  
- [ ] Xu K, Wu L, Wang Z, et al. [Graph2seq: Graph to sequence learning with attention-based neural networks](https://arxiv.org/pdf/1804.00823.pdf).2018. 
- [ ] Xu K, Wu L, Wang Z, et al. [SQL-to-text generation with graph-to-sequence model](https://arxiv.org/pdf/1809.05255.pdf)[C]. EMNLP 2018.

`Code`  
- [https://github.com/IBM/SQL-to-Text](https://github.com/IBM/SQL-to-Text)
- [https://github.com/IBM/Graph2Seq](https://github.com/IBM/Graph2Seq)
- [https://github.com/RandolphVI/Graph2Seq](https://github.com/RandolphVI/Graph2Seq)   

##### 3. 图神经网络（GNN)  

`Blog`  
- [从图(Graph)到图卷积(Graph Convolution)：漫谈图神经网络模型](https://www.cnblogs.com/SivilTaram/p/graph_neural_network_1.html)

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


