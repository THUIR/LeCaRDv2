<!--
 * @Author: lihaitao
 * @Date: 2023-02-28 23:34:00
 * @LastEditors: Do not edit
 * @LastEditTime: 2023-03-02 12:17:08
 * @FilePath: /LeCaRD2.0/LeCaRDv2/README.md
-->
# LeCaRDv2:A Large-Scale Chinese Legal Case Retrieval Dataset



## Overview

- [Introduction](#introduction)
- [Dataset Structure](#dataset-structure)
<!-- - [Install](#install) -->
- [Experiment](#experiment)
<!-- - [Evaluation](#evaluation) -->
- [Requirements](#requirements)
- [Authors](#authors)
- [License](#license)

## Introduction
LeCaRDv2 is one of the largest Chinese legal case retrieval datasets with the widest coverage of criminal charges. The dataset comprises 800 query cases and 55,192 candidate cases extracted from 4.3 million criminal case documents. We believe it can be a reliable benchmark that promotes relevant research in the field.

## Data Structure

### Query
`query.json` has 800 lines. Each line is a *dictionary* representing a query. An example of a *dictionary* is:

> {"id": 233, "query":"告石康军贩卖毒品一审判决书湖南省衡阳市珠晖区人民法院刑事判决书（2017）湘0405刑初149号：湖南省衡阳市珠晖区人民检察院以珠检公诉刑诉〔2017〕127号起诉书指控被告人石康军犯贩卖毒品罪，于2017年9月30日向本院提起公诉。本院于当日受理后，依法适用普通程序，由审判员陈东升担任审判长，与审判员阳福明、人民陪审员肖才闰组成合议庭，于2017年11月30日公开开庭审理了本案。代理书记员段佳丽担任记录。衡阳市珠晖区人民检察院指派检察员谢小芸出庭支持公诉。被告人石康军及其辩护人王剑清到庭参加诉讼......", "fact": "公诉机关指控：贩卖毒品罪被告人石康军系无业吸毒人员，以贩养吸，2017年5月至6月期间，被告人6次贩卖甲基苯丙胺（冰毒）给贩毒人员吸食共计约5.6克，查获尚未贩卖的甲基苯丙胺208.32克、甲基苯丙胺片剂3.94克。二、容留他人吸毒罪被告人石康军在其位于本市珠晖区家中，三次容留吸毒人员张某某吸食毒品甲基苯丙胺。"}

where `id` is each query's unique ID, `query` is the query content, and `fact` is the fact description of this query case.

`common_query.json`/`controversial_query.json`/`procedural_query.json` save the common query/controversial query/procedural query respectively. Details about the different types of queries can be viewed in our paper.

`train_query.json` and `test_query.json` are training data and testing data respectively, where the training data has 640 lines and the testing data has 160 lines.

### Candidates
You can download the candidate cases from this link [download](https://drive.google.com/file/d/1CqQ0ID5_9-qxaZm9TGLh38dVhLfYnl_C/view?usp=share_link).

`candidates` directory consists of 55,192 candidate documents, An example of a candidate documents is:

> {"pid": 0, "qw": "山东省武城县人民法院刑事判决书（2019）鲁1428刑初153号公诉机关山东省武城县人民检察院。被告人张宝玉，男，1983年11月出生于山东省武城县，汉族，初中肄业，户籍所在地山东省武城县，住山东省武城县......", "fact": "经审理查明：2019年7月1日7时8分，被告人张宝玉驾驶鲁Ｎ×××××号小型轿车沿宏海路由北向南行驶至腾鲁大街路口处向东转弯时，与沿宏海路由南向北行驶的徐某1驾驶、徐某2乘坐的鲁Ｎ×××××号三轮汽车相撞......", "reason": "本院认为，被告人张宝玉违反交通运输管理法规，发生重大事故，致一人死亡，且承担事故的主要责任，其行为已构成交通肇事罪，武城县人民检察院指控的事实及罪名成立，本院予以确认......", "result": "公诉机关认为，被告人张宝玉违反交通运输管理法规，发生重大交通事故致一人死亡，并承担事故的主要责任，其行为触犯了《中华人民共和国刑法》第一百三十三条之规定，犯罪事实清楚，证据确实充分，应当以交通肇事罪追究其刑事责任。其法定刑为三年以下有期徒刑或者拘役，结合其自首、认罪认罚、赔偿谅解等量刑情节，建议判处被告人张宝玉有期徒刑六个月至十个月或拘役四个月至六个月，可以适用缓刑.....", "charge": ["交通肇事罪"], "article": [133, 67, 72, 73]}

where `pid` is the ID of the case, `qw` is the full content,  `fact` is the basic facts of the case, `reason` is the analysis process of judges, `result` is the case judgment, `charge` is the criminal charge(s) of the case, `article` is the the criminal law article of this case document.

### Labels
`relevence.trec` is the relevance annotation with TREC qrels format. Specifically, each line has the `qid \t 0 \t pid \t label` format.

`relevence_gold.trec` is annotated with relevance at level 2 or higher.

## Experiment
The traditional methods are implemented with [pyserini](https://github.com/castorini/pyserini) toolkit and the code of the pre-trained model is referenced from [dense](https://github.com/luyug/Dense).




<!-- ## Evaluation -->



## Requirements

```
python=3.8
transformers==4.25.1
tqdm==4.64.1
datasets==2.8.0
torch==1.11.0
faiss==1.7.2
jieba==0.42.1
pytorch==1.12.1
pyserini==0.19.2
```

## Authors

Haitao Li liht22@mails.tsinghua.edu.cn \

Yunqiu Shao  shaoyq18@mails.tsinghua.edu.cn \

Yueyue Wu wuyueyue@mail.tsinghua.edu.cn \

Qingyao Ai aiqy@tsinghua.edu.cn \

Yixiao Ma mayx20@mails.tsinghua.edu.cn \

Yiqun Liu yiqunliu@tsinghua.edu.cn \

## License

[MIT](LICENSE) © Haitao Li