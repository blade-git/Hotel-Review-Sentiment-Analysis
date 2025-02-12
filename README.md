# 감성 분석 및 토픽 모델링 (Sentiment Analysis & Topic Modeling)
이 프로젝트는 **VADER Sentiment Analysis**를 활용하여 리뷰 데이터를 감성 분석하고, **LDA(잠재 디리클레 할당) 토픽 모델링**을 적용하여 리뷰 내용을 주제별로 분류하는 프로젝트입니다.

## 1. 프로젝트 개요 
* **목적** : 감성 분석 및 LDA 기반 토픽 모델링을 활용하여 리뷰 데이터를 보다 정교하게 분석
* **분석 대상** : 호텔 리뷰 데이터 (tripadvisor_hotel_reviews.csv)
* **출력 결과** :
  * 감성 점수와 감성 레이블을 포함한 엑셀 파일 (VADER_Sentiment_Analysis_Results.xlsx) 생성
  * pyLDAvis를 활용한 토픽 시각화 제공

## 2. 사용된 기술 및 라이브러리
* **Python 3.11.8**
* **VADER
