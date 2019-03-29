---
title: "bert-as-service"
date: 2019-03-29 00:00:00 -0900
categories: ML Engineer
---

* bert-as-service
  * Sentence 인코딩 서비스 (BERT 모델) 
  * 사이트: https://github.com/hanxiao/bert-as-service
  
* 설치
  * $ pip install bert-serving-server  # server
  * $ pip install bert-serving-client  # client, independent of `bert-serving-server`
* 서버 실행
  * $ bert-serving-start -model_dir ./multi_cased_L-12_H-768_A-12 -num_worker=4 
  
* Example Client 
from bert_serving.client import BertClient
bc = BertClient()
bc.encode(['First do it', 'then do it right', 'then do it better'])
