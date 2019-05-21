# Greatest-Classify-Group
Respiratory Diseases Classification Using Audio Data



## 190503 - 개발환경 구축, 측정 부위별 데이터 분류 및 시각화
```
[진행사항]

김기홍 : 개발환경 구축
김동익 : 측정 부위별 데이터 분류 및 시각화(스펙트로그램 이미지)
이가경 : 측정 부위별 데이터 분류 및 시각화(스펙트로그램 이미지)
이상민 : 개발환경 구축

[향후계획]
질병 유무 판단 구현 이후 분류 문제 구현
1. MFCC 전처리 후 SVM 학습
2. Mel spectrogram 이후 CNN 학습
3. Colab, jupyter에서 파일을 한번에 로드하는 방법 알아오기

[질문]
Training Data, Test Data 나누는 기준 여쭤보기
학습을 위한 186개 데이터를 한꺼번에 로드하는 방법(path를 통해 혹은 Mnist 이미지 처럼 한 이미지안에 여러 이미지)

참고 사이트
http://keunwoochoi.blogspot.com/2016/12/3.html(음성/음악신호 + 머신러닝 초심자를 위한 가이드)
https://blog.naver.com/jamiet1/221409527938 (내 이미지 데이터로 CNN구현)
```

## 190506 - 자료조사, 피쳐추출, 학습방법 회의 
```
아픈 사람과 아프지 않은 사람의 소리가 어떻게 다른지 직접 데이터를 듣고, 그래프를 봐서 정리해오기로 결정
> 다음 회의 화요일 밤10시 - 11시

[향후계획]
1. 어떤 필터 과정이 정확하게 필요한지(스펙트럼을 추출하는 과정 : window, mel, mfcc, stft, log)
2. 필터 거친 음원 어떻게 CNN에 적용할지

[발견한 문제 가설]
아픈 환자의 폐소리가 부위별로 다른 건강 상태를 나타낼 수 있는가?
1번 부위 폐소리 > 아픔. 2번 부위의 소리 > 건강 할 수 있는지?

이럴경우 환자가 2번 폐소리만 input으로 가져올 경우
> 정상이라 판단하는 문제가 생길 수 있음
```

*각자 역할 보충바람
## 190510 - 음성데이터 파일 Feature 추출 방법 조사 및 CNN학습 과정 설계
```
김기홍 : 자체 이미지를 활용한 MNist 파일을 만들기 위해 이미지 폴더 내 파일 축소 및 확대 방법 조사, 이미지를 숫자형 데이터로 변환하는 방법 조사, CNN 학습과정 설계
김동익 : MFCC 관련 자료조사
이가경 : MFCC 코딩
이상민 : MFCC 코딩
```

## 190515 - 음성데이터 파일 MFCC 처리 후 CNN 학습 진행
```
187개 파일 임의로 0,1 train, test 파일로 나눈 후 학습 진행 결과
0.7222222 정확도를 얻음
```

## 190517 - 자료정리 및 내주 계획 작성
```
05/24 오전 11시부터 팀플
1. Multi Channel까지 데이터 늘려보기
2. 정확도 향상되는 정도를 보고 분류작업까지 진행할지 결정

정확도 향상을 위한 방법 고안

1. 이미즈 사이즈 조절에 따른 정확도
2. 데이터량 증가시키기
3. MFCC > 학습, MFCC+delta > 학습
4. Sampling rate 조절
5. Validation을  어떻게 구성할것인지
```
