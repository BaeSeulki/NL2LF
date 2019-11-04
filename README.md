## NL2LF
> The Resources for "Natural Language to Logical Form" Research;  
> "自然语言转逻辑形式"研究资料收集: 本阶段主要以NL2SQL的研究为主, 主要包括评测公开数据集、相关论文和部分代码实现、相关博客或公众号文章。

### NL2SQL
#### 主要评测数据集
---
- **Academic, Advising, ATIS, Geography, Restaurants, Scholar, IMDB, Yelp, etc.**  
  - `Blog` [http://jkk.name/text2sql-data/](http://jkk.name/text2sql-data/) 
  - `GitHub` [https://github.com/jkkummerfeld/text2sql-data](https://github.com/jkkummerfeld/text2sql-data)
  - `Paper` [Improving Text-to-SQL Evaluation Methodology](https://www.aclweb.org/anthology/P18-1033.pdf), _Finegan-Dollak C, Kummerfeld J K, Zhang L, et al._, ACL 2018  
---
- **WikiTableQuestions**
  - `Home` [WikiTableQuestions: a Complex Real-World Question Understanding Dataset](https://nlp.stanford.edu/blog/wikitablequestions-a-complex-real-world-question-understanding-dataset/)

---
- **WikiSQL**  
  > WikiSQL数据集特点:
  > 1. 单表单列查询; 
  > 2. 聚合操作('MAX', 'MIN', 'COUNT', 'SUM', 'AVG'); 
  > 3. 条件连接('AND'); 
  > 4. 条件比较('=', '>', '<')
  - `GitHub` [https://github.com/salesforce/WikiSQL](https://github.com/salesforce/WikiSQL)
  - `Paper` [Seq2sql: Generating structured queries from natural language using reinforcement learning](https://arxiv.org/pdf/1709.00103.pdf), _Zhong V, Xiong C, Socher R._ , 2017.

---
- **Spider**  
  > Spider数据集特点:
  > 1. Complex, Cross-domain and Zero-shot 
  > 2. 多表多列查询, 复杂子查询;
  > 3. 聚合操作('MAX', 'MIN', 'COUNT', 'SUM', 'AVG'); 
  > 4. 条件连接('AND','OR'); 
  > 5. 条件比较('=', '>', '<')
  > 6. 条件操作('JOIN', GROUP BY', 'ORDER BY', 'HAVING', 'LIMIT')
  - `Home` [https://yale-lily.github.io/spider](https://yale-lily.github.io/spider)
  - `GitHub` [https://github.com/taoyds/spider](https://github.com/taoyds/spider)
  - `Paper` [Spider: A Large-Scale Human-Labeled Dataset for Complex and Cross-Domain Semantic Parsing and Text-to-SQL Task](https://arxiv.org/pdf/1809.08887.pdf) _Yu T, Zhang R, Yang K, et al._ , EMNLP 2018.

---
- **SParC**
  > SParC数据集特点:
  > 1. Context-dependent and Multi-turn version of the Spider task.  
       继承Spider特点的上下文多轮任务。
  - `Home` [https://yale-lily.github.io/sparc](https://yale-lily.github.io/sparc)
  - `Paper`[SParC: Cross-Domain Semantic Parsing in Context](https://arxiv.org/pdf/1906.02285.pdf), _Yu T, Zhang R, Yasunaga M, et al._, ACL 2019.

---
- **CoSQL**
  > CoSQL数据集特点: 
  > 1. Cross-domain Conversational, the Dilaogue version of the Spider and SParC tasks.
  >    继承Spider特点的多轮对话任务，涉及意图澄清。
  - `Home` [https://yale-lily.github.io/cosql](https://yale-lily.github.io/cosql)
  - `Paper` [CoSQL: A Conversational Text-to-SQL Challenge Towards Cross-Domain Natural Language Interfaces to Databases](https://arxiv.org/pdf/1909.05378.pdf), _Yu T, Zhang R, Er H Y, et al._, EMNLP2019 

---
- **Chinese Spider**
  > 中文版Spider，数据待发布
  - `Paper` [A Pilot Study for Chinese SQL Semantic Parsing](https://frcchang.github.io/pub/emnlp2019.2.pdf), _Qingkai Min, Yuefeng Shi and Yue Zhang_, EMNLP 2019.

---
- **TableQA** 
  > 首届中文NL2SQL挑战赛 
  > 数据特点:
  > 1. 中文加强版WikiSql，金融等泛领域数据
  > 2. 单表多列(两列)查询
  > 3. 聚合操作('MAX', 'MIN', 'COUNT', 'SUM', 'AVG'); 
  > 4. 条件连接('AND', 'OR'); 
  > 5. 条件比较('=', '>', '<', '!=')
  - `Home` [https://tianchi.aliyun.com/competition/entrance/231716/information](https://tianchi.aliyun.com/competition/entrance/231716/information)
  - `Blog` 
     1. [让机器自动写SQL语言，首届中文NL2SQL挑战赛等你来战](https://mp.weixin.qq.com/s/wuC8O6DuxxtuFe8BO1ilZQ)
     2. [一图读懂首届中文NL2SQL挑战赛](https://mp.weixin.qq.com/s/0FhfX0r643umZ36HxffLmQ)
     3. [首届中文NL2SQL挑战赛圆满结束，产学研携手共推智能交互发展](https://mp.weixin.qq.com/s/F747u_n3vVC2y8Z1dOaoNw)
  - `PPT` 
     1. [TOP5] 