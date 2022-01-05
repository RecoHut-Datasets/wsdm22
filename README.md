
# WSDM Cup (2022) on Cross-Market Recommendation Competition

There are three folders s1, s2, and s3; containing the data of the source markets. Inside each, the following files can be found:
- train.tsv and train_5core.tsv: A tab separated file, containing the Training data with the following format: userId itemId rating where the first column userId is the user unique id, the second column itemId is the item unique id, and the third column rating is the rating (an integer ranging from 1 to 5). We conduct some pre-processing steps and provide 5core versions for training data for further facilitate the data preprocessing burden. For this step, we first normalize ratings into 0 and 1 and filtered users with 5 ratings, and items with 5 ratings from their corresponding train.tsv file. Note that you might see some descripincies between these training files. It is due to a few other steps that is related to our data generation and we are not able to reveal those. This means that our 5core training data only contains the positive samples. All the other (user, item) pairs are unknown and can be considered negative during training. We provide valid_qrel.tsv and valid_run.tsv for source markets for any solution that might need evalutions on source markets.

There are two folders t1, and t2; containing the data of the target markets. Inside each, the following files can be found:
- train.tsv and train_5core.tsv: Similar to source markets, provide tab separated files, containing the Training data with userId, itemId, and rating fields.
- valid_qrel.tsv: The Validation positive samples, with a structure similar to the train.tsv. Note that the validation set only has one positive sample per user.
- valid_run.tsv: The Validation samples. For consistency of results between different teams, we provide you 99 negative samples for each unique userId as follows: userId itemId1,itemId2,...,itemId100 where the two columns are separated by a tab and the list of items are separated by commas. There are 99 negative samples and 1 positive sample (identified in the valid_qrel.tsv file) in the list. Your model should rerank these 100 items per user.
- test_run.tsv: The Test candidate samples. As is common in recommendation systems, we provide you 100 candidate items for each unique userId as follows: userId itemId1,itemId2,...,itemId100 where the two columns are separated by a tab and the list of negative items are separated by commas. These 100 items should be reranked by your models and the top 10 items for each user should be reported with their scores. Note that only one item from this list of 100 items is a positive sample and the rest 99 items are negative samples.

## Tree

```
.
├── [ 27M]  s1
│   ├── [1.8M]  train_5core.tsv
│   ├── [ 19M]  train.tsv
│   ├── [139K]  valid_qrel.tsv
│   └── [5.6M]  valid_run.tsv
├── [ 10M]  s2
│   ├── [1.1M]  train_5core.tsv
│   ├── [2.6M]  train.tsv
│   ├── [153K]  valid_qrel.tsv
│   └── [6.2M]  valid_run.tsv
├── [4.7M]  s3
│   ├── [548K]  train_5core.tsv
│   ├── [1.2M]  train.tsv
│   ├── [ 72K]  valid_qrel.tsv
│   └── [2.9M]  valid_run.tsv
├── [6.6M]  t1
│   ├── [2.3M]  test_run.tsv
│   ├── [460K]  train_5core.tsv
│   ├── [1.4M]  train.tsv
│   ├── [ 58K]  valid_qrel.tsv
│   └── [2.3M]  valid_run.tsv
├── [180K]  t1t2
│   └── [176K]  valid_qrel.tsv
└── [ 13M]  t2
    ├── [4.8M]  test_run.tsv
    ├── [966K]  train_5core.tsv
    ├── [2.8M]  train.tsv
    ├── [118K]  valid_qrel.tsv
    └── [4.8M]  valid_run.tsv

  62M used in 6 directories, 23 files
```

## References
- [https://xmrec.github.io/wsdmcup](https://xmrec.github.io/wsdmcup/)
- [https://github.com/hainguyentado/recsys-xmrec-team10](https://github.com/hainguyentado/recsys-xmrec-team10)
- [https://competitions.codalab.org/competitions/36050](https://competitions.codalab.org/competitions/36050)
- [https://github.com/hamedrab/wsdm22_cup_xmrec](https://github.com/hamedrab/wsdm22_cup_xmrec)