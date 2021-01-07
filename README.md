# NLP
nlp 관련하여 개인 실습 및 수업시간의 실습 모음

## 프레임워크와 라이브러리
### Gensim
- 토픽 모델링과 자연어 처리등을 수행할 수 있게 해주는 오픈 소스 라이브러리
- Gensim을 사용하여 Topic Modeling과 Word2Vec등을 학습

## 자연어 패키지
### NLTK(Natural Language Toolkit)
자연어처리를 위한 파이썬 패키지  
아나콘다에 NLTK 기본적으로 설치되어있음  

### KoNLPy
한국어 자연어 처리를 위한 형태소 분석기 패키지

## Pandas: 파이썬 데이터 처리를 위한 라이브러리  
세가지 데이터 구조
- Series "index", "value"
- DataFrame "index", "column", "value"
- Panel

## numpy: 수치 데이터를 다루는 파이썬 패키지
Numpy의 주요 모듈
- np.array() #리스트, 튜플, 배열로부터 ndarray를 생성
- np.asarray() #기존의 array로부터 ndarray를 생성
- np.arange() #range와 비슷
- np.linspace(start, end, num) #[start, end] 균일한 간격으로 num개 생성
- np.logspace(start, end, num) #[start, end] log scale간격으로 num개 생성  
연산을 각 인덱스마다 해줌

## Pandas-Profiling - EDA에 좋음
```
pip install -U pandas-profiling
```

```python
import pandas as pd
import pandas_profiling

data = pd.read_csv("spam.csv 파일의 경로', encoding = 'latin1')
pr = data.profile_report() #프로 파일링 결과 리포트를 pr에 저장
pr.to_file('./pr_report.html') #pr_report.html 파일로 저장
pr #pr에 저장했던 리포트 출력
```



## 텍스트 전처리(Text Preprocessing)
### 토큰화(Tokenization)
```python
from nltk.tokenize import word_tokenize
print(word_tokenize("Don't be fooled by the dark sounding name"))
```
```python
from nltk.tokenize import word_tokenize
text="I am actively looking for Ph.D. students. and you are a Ph.D. student."
print(word_tokenize(text))

from nltk.tag import pos_tag
x=word_tokenize(text)
pos_tag(x)

from konlpy.tag import Okt  
okt=Okt()  
print(okt.morphs("열심히 코딩한 당신, 연휴에는 여행을 가봐요"))
print(okt.pos("열심히 코딩한 당신, 연휴에는 여행을 가봐요"))  
print(okt.nouns("열심히 코딩한 당신, 연휴에는 여행을 가봐요"))  
```
- morphs:형태소 추출
- pos: 품사태깅
- nouns: 명사 추출

### 정제(Cleaning) & 정규화(nomalization)
- Cleaning: 갖고 있는 코퍼스로부터 노이즈 데이터 제거
- Normalization: 표현 방법이 다른 단어들을 통합시켜서 같은 단어로 만들어줌

### 어간 추출(Stemming) & 표제어 추출(Lemmatization)

### 불용어(Stopword)
```python
from nltk.corpus import stopwords 
from nltk.tokenize import word_tokenize 

example = "Family is not an important thing. It's everything."
stop_words = set(stopwords.words('english')) 

word_tokens = word_tokenize(example)

result = []
for w in word_tokens: 
    if w not in stop_words: 
        result.append(w) 
```

### 정규 표현식(Regular Expression)
- 병렬 연산을 위해서 여러 문장의 길이를 임의로 동일하게 맞춰주는 작업

### 정수 인코딩(Integer Encoding)
### 패딩(Padding)
### 원-핫 인코딩(One-Hot Encoding)
### 데이터의 분리(Splitting Data)

## Language Model
단어 시퀀스(문장)에 확률을 할당하는 모델  
언어 모델을 만드는 방법은 **1) 통계에 기반한 전통적인 언어모델(Statistical Language Model(SLM))** & **2) 인공신경망을 이용한 방법**  

- SLM
- N-gram 언어 모델
- 한국어에서의 언어모델 
- Perplexity
- 조건부 확률

## 카운트 기반의 단어 표현
- Bags of Words(BoW)
- 문서 단어 행렬(Document-Term Matrix, DTM) 
- TF-IDF(Term Frequency-Inverse Document Frequency)

## 문서 유사도(Document Similarity) 
- 유클리드 유사도(euclidean distance) 
- 자카드 유사도(Jaccard Similarity) -> 행렬에서
- 코사인 유사도(Cosione Similarity)

## Topic Modeling
### 잠재 의미 분석(Latent Semantic Analysis, LSA)
### 잠재 디리클레 할당(Latent Dirichlet Allocation, LDA)

## 



