# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 장주휘
- 리뷰어 : 유비


# PRT(Peer Review Template)
- [x]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 잘 첨부되었음
      <img width="746" height="709" alt="1" src="https://github.com/user-attachments/assets/e3302a5d-9095-4ba5-a468-4367bcb8fcf5" />
      <img width="765" height="568" alt="2" src="https://github.com/user-attachments/assets/cde8cc4e-e07b-43eb-9fb5-103789603c7b" />
      <img width="757" height="572" alt="3" src="https://github.com/user-attachments/assets/6b2c729a-1eba-4bf8-934a-41d7a3406e7a" />

    
- [x]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - RNN에서 pre패딩이 중요한 이유를 구현으로 풀어냄
    - 해당 코드 블럭에 doc string/annotation이 달려 있음
    - 해당 코드의 기능, 존재 이유, 작동 원리 등을 잘 기술했음
    - 주석을 보고 코드 이해가 잘 되었음
    - ex) (문장을 뒤집어서 post 패딩을 한 뒤, 다시 뒤집으면 깔끔하게 pre 패딩이 됩니다)
       <img width="484" height="488" alt="4" src="https://github.com/user-attachments/assets/49f864a9-3091-4f3b-a8ae-cf38dba8f985" />

        
- [x]  **3. 에러가 난 부분을 디버깅하여 문제를 해결한 기록을 남겼거나
새로운 시도 또는 추가 실험을 수행해봤나요?**
    - Word2Vec 경로 FileNotFoundError를 여러 후보 경로 자동 탐색(candidates 리스트)으로 해결
    - 과적합, 최적 체크포인트 분석 그래프를 따로 그림(평균+2σ, optimal epoch 표시)
        <img width="747" height="834" alt="5" src="https://github.com/user-attachments/assets/d8eb4811-4c65-400f-bcd3-b91512f68298" />
        <img width="452" height="458" alt="6" src="https://github.com/user-attachments/assets/e4969bf2-6565-4653-82f3-eaeb5024504e" />

        
- [x]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 잘 기록되어 있음
    - 흐름도를 나타내는 그래프는 없지만 모델별 그래프는 존재함
      <img width="366" height="170" alt="7" src="https://github.com/user-attachments/assets/81f89220-6102-4939-b657-b3842164f2f9" />
      <img width="746" height="709" alt="1" src="https://github.com/user-attachments/assets/ed9f6262-c1b9-49ee-b8c8-561712c7e55d" />
      <img width="765" height="568" alt="2" src="https://github.com/user-attachments/assets/0965f88e-faa1-426a-aec0-9c95bb077b6f" />
      <img width="757" height="572" alt="3" src="https://github.com/user-attachments/assets/994ad71b-554e-43e2-9574-416a1927014e" />

        
- [x]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 잘 준수하였음
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화하여 중복을 제거했음
    - train_and_evaluate 함수 하나로 3개 모델 학습, 검증, 그래프, 테스트를 전부 처리
      <img width="328" height="75" alt="8" src="https://github.com/user-attachments/assets/25e9783d-5fee-4d69-9cd1-9a48bb40b16c" />



# 회고(참고 링크 및 코드 개선)
```
[리뷰어 회고]
패딩 길이를 '평균+2σ'로 통계적으로 결정한 점 — 눈대중이 아닌 근거 기반으로 결정한 것으로 보인다
train_and_evaluate 함수 하나로 모델 3개를 깔끔히 돌린 모듈화 부분에서 다음 프로젝트에서 나 자신의 채울점을 찾았다
Word2Vec 경로 에러를 후보 경로 자동 탐색으로 견고하게 처리한 디버깅한 것이 인상적이었다
Mecab 설치 시에 리뷰어는 mecab-python3으로 우회했는데 엔진을 직접 빌드하여 정석적인 설치법을 사용한 것도 인상적이었다
(시간과 귀찮음 이슈로 시도 끝에 우회를 선택함...)

분류 정확도는 높지만 자체 임베딩의 단어 유사도는 부실하다
= 모델이 의미가 아니라 긍/부정 키워드를 학습했다는 분석을 하여 이해하는 모습을 보였다

[개선 제안]
- Word2Vec을 유사단어 확인이 끝이 아닌, 실제 임베딩 초기값으로 넣어 학습한 결과가 있으면 더 좋았을 것으로 보인다
```
