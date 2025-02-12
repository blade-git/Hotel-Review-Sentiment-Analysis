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
* **VADER**
* **Pandas** (데이터 처리 및 엑셀 파일 저장)
* **토픽 모델링** (LDA) (sklearn.feature_extraction.text.CountVectorizer & sklearn.decomposition.LatentDirichletAllocation)
* **토픽 시각화** (pyLDAvis 활용)
* **불용어 제거** (nltk.corpus.stopwords 활용)
* **CSV 파일 로드 및 저장**

## 3. 노트북 실행
* **감성분석_모델.ipynb** 파일을 열고 실행하면 감성 분석 결과가 엑셀 파일로 저장됩니다.
* pyLDAvis를 활용한 **토픽 시각화**를 통해 주요 주제와 감성 분석 결과를 확인할 수 있습니다.

## 4. 데이터 설명
### 1. 감성 분석 데이터
* 감성 분석은 **VADER Sentiment Analysis**를 이용하여 **텍스트의 감성 점수를 계산**합니다.
* 주요 컬럼 :
  * **Review** : 사용자의 리뷰 텍스트
  * **VADER_Score** : 감성 점수 (-1 ~ 1)
  * **Sentiment** : 감성 분류 (Positive, Negative, Neutral)
* 분석 결과는 VADER_Sentiment_Analysis_Results.xlsx 파일에 저장됩니다.

### 2. 토픽 모델링 및 주제별 감성 분석 데이터
* 토픽 모델링은 **LDA(잠재 디리클레 할당) 알고리즘**을 활용하여 리뷰 데이터를 **주제(Topic)별로 분류**합니다.
* 각 주제별 감성 분석을 수행하여 **주제별 감정 비율(긍정/부정 비율)을 계산**합니다.

## 5. 토픽 모델링 및 주제별 감성 분석 과정
### 1. 텍스트 전처리
* 리뷰 데이터를 **소문자로 변환**하고, **불용어를 제거한 후 벡터화**합니다.
* **CountVectorizer**를 사용하여 **문서-단어 행렬을 생성**합니다.
### 2. LDA 모델 학습
* **LatentDirichletAllocation(n_components=5)**를 사용하여 **5개의 주제(Topic)로 분류**합니다.
* **fit_transform()**을 통해 **LDA 모델을 학습**합니다.
### 3. 주제별 감성 분석 수행
* **VADER SentimentIntensityAnalyzer()**를 활용하여 각 리뷰의 감성 점수를 계산합니다.
* 각 리뷰를 **긍정(Positive)**,**부정(Negative)**,**중립(Neutral)**으로 분류합니다.
* 각 주제(Topic)별로 감성 분석을 수행하여, **주제별 감성 비율(긍정/부정 비율)을 계산**합니다.
### 4. 주제별 주요 단어 및 감성 분석 결과 출력
* 각 주제별로 **가장 중요한 10개의 단어를 출력**하여, 해당 주제의 특징을 파악합니다.
* 각 주제별로 **긍정 및 부정 감성 비율을 계산**하여 **topic_sentiment_summary**를 생성합니다.

## 6. 파일 저장
* 감성 분석 결과 : **VADER_Sentiment_Analysis_Results.xlsx**
* 토픽 시각화 결과 : **pyLDAvis** HTML 파일로 저장 가능
* **pyLDAvis**를 활용하여 **LDA 모델의 주요 토픽을 시각화**할 수 있습니다.
* 실행 후 브라우저에서 주제 분석을 확인할 수 있습니다.
