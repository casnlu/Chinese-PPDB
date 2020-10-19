# Chinese-PPDB
Chineses PPDB (Chinese paraphrase database)是一个自动抽取大规模中文复述语料库。
复述是对相同语义的不同字面表述，是语言多样性的集中体现。
创建该语料库的目标是增强自然语言处理方法应对中文语言多样性的问题，提升模型的鲁棒性和泛化性。

与[PPDB](http://paraphrase.org/)语料库类似，该语料库包含词汇、短语、模版和句子四种粒度的复述数据。



Chineses PPDB是一个处于起步阶段的语料库，后续会不断的增加语料库的规模，包含的特征、不同的相似度度量的特征等。

# 文件格式
与PPDB不同，该语料库以JSON格式作为数据存储的主要格式，以便于后续的读取和使用。对于单条复述其格式如下：
```json
{
    "type":"type",
    "phrase":"text",
    "paraphrase":"text",
    "from":"",
    "features":{},
    "alignment":"",
    "entailment":""
}
```

其中type是该复述数据的类型，包括lexical、phrase、template和sentence四种类型；phrase是词、短语或模版，paraphrase是对应的复述，from字段是该该数据的来源，目前的主要来源包含：双语平行数据、单语对齐数据。
features字段是对该复述对的一些特征，例如编辑距离、词向量相似度等，包含多种特征。特征的列表及其说明在[features.md](https://github.com/cipnlu/Chinese-PPDB/blob/main/features.md)文件中详细描述。
alignment字段是两个复述对在词一级的对齐；
entailment字段是参考PPDB给出的句子对是否为等价语义。


该数据集的[英文](https://github.com/cipnlu/Chinese-PPDB/blob/main/README.en.md)介绍。

# TODO
1. 增加特征信息
2. 扩充数据集
3. 基于已有特征使用回归算法得到分类排序
4. 构建复述识别Benchmark工具库
5. 构建复述生成Benchmark工具库


# 版权信息

1. Chinese PPDB面向国内外大学、研究所、企业以及个人研究者免费开放源。
2. 如有机构或个人拟将Chinese PPDB用于商业目的，请发邮件至anbo724@gmail.com洽谈技术许可协议。
3. 欢迎对该工具包的任何宝贵意见和建议，请发邮件至anbo724@gmail.com。
4. 如果您在THUCTC基础上发表论文或取得科研成果，请您在发表论文和申报成果时声明“使用了中国科学院软件研究所中文信息处理Chinese PPDB语料库”

# 相关论文
1. Juri Ganitkevitch, Benjamin Van Durme, Chris Callison-Burch. PPDB: The Paraphrase Database. Proceedings of the 2013 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies (NAACL 2013), 2013, pp 758–764


# 作者
Bo An (安波，助理教授)，Xianpei Han (韩先培，导师), Le Sun (孙乐，导师)，Yaozu Sun(孙耀祖，硕士生)



