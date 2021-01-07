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
- 토큰화(Tokenization)
- 정제(Cleaning) & 정규화(nomalization)
- 어간 추출(Stemming) & 표제어 추출(Lemmatization)
- 불용어(Stopword)
- 정규 표현식(Regular Expression)
- 정수 인코딩(Integer Encoding)
- 패딩(Padding)
- 원-핫 인코딩(One-Hot Encoding)
- 데이터의 분리(Splitting Data)
- 한국어 전처리 패키지

