### Lec 12: NN의 꽃 RNN 이야기

---

- Sequence data : 현재 state가 다음 state에 영향을 미친다

  ![img](../resources/img/0603/img1.png)

- Recurrent Neural Network

  ![img](../resources/img/0603/img2.png)

- hello 데이터를 받았을 때,

  ![img](../resources/img/0603/img3.png)

- one-hot Encoding으로 벡터화

  ![img](../resources/img/0603/img4.png)

- Softmax를 이용한 결과 추론 

  ![img](../resources/img/0603/img5.png)

-  RNN 활용

  ![img](../resources/img/0603/img6.png)

  - Language Modeling : 연관 검색어
  - Speech Recognition 
  - Maching Translation : 번역 
  - Conversation Modeling/Question Answering : 챗봇
  - Image/Video Captioning 
  - Image/Music/Dance Generation :

- 복잡한 RNN 처리 : LSTM, GRU

---

### Lab 12-0 rnn basics

- 