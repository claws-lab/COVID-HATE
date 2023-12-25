## Racism is a Virus: Anti-Asian Hate and Counterspeech in Social Media during the COVID-19 Crisis (IEEE/ACM ASONAM 2021)
#### Authors:[Bing He](http://claws.cc.gatech.edu/covid), [Caleb Ziems](http://calebziems.com/), [Sandeep Soni](http://sandeepsoni.github.io/), [Naren Ramakrishnan](https://dac.cs.vt.edu/person/naren-ramakrishnan/), [Diyi Yang](https://www.cc.gatech.edu/~dyang888/), [Srijan Kumar](https://www.cc.gatech.edu/~srijan/)

----
If you make use of this code, the algorithm, or the datasets in your work, please cite the following paper 
(to be updated when we have the official bib from IEEE/ACM ASONAM 2021):

```
@inproceedings{he2021racism,
  title={Racism is a virus: Anti-Asian hate and counterspeech in social media during the COVID-19 crisis},
  author={He, Bing and Ziems, Caleb and Soni, Sandeep and Ramakrishnan, Naren and Yang, Diyi and Kumar, Srijan},
  booktitle={Proceedings of the 2021 IEEE/ACM International Conference on Advances in Social Networks Analysis and Mining},
  pages={90--94},
  year={2021}
}
```

----

#### All the code and data can be downloaded by this [link](https://www.dropbox.com/sh/g9uglvl3cd61k69/AACEk2O2BEKwRTcGthgROOcWa?dl=0) .
1. Note that the code and data from the previous arxiv version is out of date. Please use this latest dataset.
2. We also find some of the tweets have been deleted. If you need to use the whole dataset for the research project, please contact the author Bing He(bhe46@gatech.edu). We can help you get the data properly.
3. We notice the change of Twitter API, and some of you may not have access to the data. If you want to get the whole data, please contact the author Bing He (bhe46@gatech.edu). We can share it with you.



Given a tweet id, if you want to get the tweet text, the user who sends this tweet and other information, please use Twitter API to pull this information. [link](https://developer.twitter.com/en/docs/twitter-api) .


The detailed explanation is as follows:

----
## Data

#### Annotated tweets
- file: `annotated_tweets.csv`
- format: it contains three columns: `Tweet ID` and `label`
- label: 0 means neutral, 1 means counterhate, and 2 means hatespeech}

#### Classified tweets
- file: `asonam_release_all_tweets.csv`
- format: it has two columns: `Tweet ID` and `Bert_label`
- label: {0: neutral, 2: hatespeech, 1: counterhate}

#### User network
- files: we provide the latest user networks: `user_following.tar.gz` and `user_followers.tar.gz`.
- format: for user0 whose corresponding id is user0_id, 
  the file of the following/follower network is user0_id.json, and
  the detailed format is {"ids": [user1_id, user2_id, user3_id]},
  indicating user0 follows or is followed by user1, user2 and user3.
----
## Code

#### Requirement
- `requirements.txt` contains the whole package requirement and
we can use `pip install -r requirements.txt` to install the packages.

#### Classifier
- python file: `run-bert.py`
- command: `python run-bert.py --input tweet.csv --output classified_tweet.csv  --gpu 0 --logfile log.txt --trainedBertModel ./bert-8-3-5`
- input tweet.csv requirement: one column called "Text" containing the tweet text
- other parameters: `gpu` specifies the GPU id, `logfile` records what file has been processed, `trainedBertModel` is the trained Bert model.
- trained Bert models: `bert-8-3-5.tar.gz`

----
## Contact

if you have any questions, please feel free to contact Bing He (bhe46@gatech.edu)