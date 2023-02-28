<!--
 * @Author: lihaitao
 * @Date: 2023-02-28 23:34:00
 * @LastEditors: Do not edit
 * @LastEditTime: 2023-02-28 23:44:02
 * @FilePath: /LeCaRD2.0/LeCaRDv2/README.md
-->
# LeCaRDv2:A Large-Scale Chinese Legal Case Retrieval Dataset



## Overview

* [Introduction](#introduction)
- [Dataset Structure](#dataset-structure)
- [Install](#install)
- [Experiment](#experiment)
- [Evaluation](#evaluation)
- [Requirements](#requirements)
- [Authors](#authors)
- [License](#license)

## Introduction

LeCaRDv2 is one of the largest Chinese legal case retrieval datasets with the widest coverage of criminal charges. The dataset comprises 800 query cases and 55,192 candidate cases extracted from 4.3 million criminal case documents. We believe it can be a reliable benchmark that promotes relevant research in the field.

## Data Structure

### Query
`query.json` has 800 lines. Each line is a *dictionary* representing a query. An example of a *dictionary* is:

> {"id": 794, "query": "姚帝锋抢劫罪一审刑事判决书重庆市北碚区人民法院刑事判决书（2019）渝0109刑初483号：重庆市北碚区人民检察院以渝碚检刑诉〔2019〕439号起诉书指控被告人姚帝锋犯抢劫罪，向本院提起公诉。本院适用刑事案件速裁程序，实行独任审判，公开开庭审理本案公诉机关指控，2019年5月31日22时许，被告人姚帝锋预谋抢劫后来到重庆市北碚区七一桥路段，对独自步行的被害人王某进行尾随，尔后用左手持美工刀卡住王某的脖子对其进行威胁并索要现金，因王某未携带现金，姚帝峰未劫得财物。姚帝峰逃离现场后将上述美工刀丢弃于北碚区龙凤桥下龙凤溪中。2019年6月4日，被告人姚帝锋被公安民警抓获归案，其归案后如实供述了公安机关已掌握的上述犯罪事实。公诉机关认为，被告人姚帝锋以非法占有为目的，当场使用暴力抢劫他人财物，其行为触犯了《中华人民共和国刑法》第二百六十三条，犯罪事实清楚，证据确实、充分，应当以抢劫罪追究其刑事责任。鉴于被告人姚帝锋已经着手实行犯罪，由于意志以外的原因而未得逞，系犯罪未遂，对其处罚时还应当适用《中华人民共和国刑法》第二十三条的规定可以比照既遂犯从轻或者减轻处罚;姚帝锋如实供述自己的罪行，对其处罚时还应当适用《中华人民共和国刑法》第六十七条第三款的规定可以从轻处罚。建议判处被告人姚帝锋有期徒刑二年，宣告缓刑四年，并处罚金2000元。被告人姚帝锋对公诉机关指控的事实、罪名及量刑建议无异议且签字具结"}


### Candidates

### Labels



## Experiment



## Evaluation



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