# Open-source-AI 14조
오픈소스AI응용 14조 기말팀플과제



## 요구사항
- OS : windows 64bit
- Python version : 3.11
- 사용된 라이브러리 (pip install로 설치 필요)
  - bs4 (4.12.2)
  - youtube_transcript_api
  - nltk (3.8.1)
  - selenium 
  - gensim

## 파일별 설명 및 실행방법
### chrome-win64 폴더
- 테스트용 chrome.exe가 들어있는 폴더.
- 개별 로컬 pc에 설치되어있는 크롬 버전이 다르거나 아예 크롬이 설치되어 있지 않을때 발생 가능한 문제를 없애기 위해 포함.
- 버전 : 119.0.6045.105
### chromedriver-win64 폴더
- 크롬드라이버가 들어있는 폴더.
- chrome.exe의 버전과 일치해야 에러가 발생하지 않음.
- 버전 : 119.0.6045.105
### youtube_url_to_heatmap_coordinates.py
- 유튜브 url을 집어넣으면, 히트맵 좌표를 return해주는 코드
- 맨 아래 주석처리되어있는 test code 주석을 풀고, 테스트해볼 수 있다
- 아래와 같이 다른 파이썬 코드에 import해서 사용
  ```python
  import youtube_url_to_heatmap_coordinates as heatmap
  print(heatmap.youtube_url_to_heatmap_coordinates(url))
  ```
### test.py
- 테스트용 코드 (계속 수정될 예정)
- youtube_url_to_heatmap_coordinates.py를 import함.
- 세 개의 url에 대해 히트맵그래프 정보를 받아와 다듬어 출력하는 코드.

### word_tokenize.py
- youtube_transcript_api를 사용해 유튜브 스크립트를 받아옴.
- 받아온 스크립트를 문장별로 word-tokenize해서 출력
- 토큰화 과정은 현재는 다른 라이브러리 사용 + 수작업이지만, 후에 SBERT 등을 사용한 토큰화로 대체할 예정

### word2vec.py
- 마찬가지로 SBERT 사용할 시 word2vec을 사용할 이유가 없으므로 삭제할 예정.

## 추가할 것
- SBERT
- x,y 데이터 라벨링하는 코드
- 처리완료한 데이터를 넣어서 학습시킬 regression 모델 개발
