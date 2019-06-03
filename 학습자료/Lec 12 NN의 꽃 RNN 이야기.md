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

- keras를 활용한 RNN 구현

  - 1번째 방법

    ```
    cell = layers.SimpleRNNCell(units=hidden_size) rnn = layers.RNN(cell, return_sequences=True, return_state=True)
    outputs, states = rnn(x_data)
    ```

  - 2번째 방법

    ```
    rnn = layers.SimpleRNN(units=hidden_size, return_sequences=True, return_state=True) 
    outputs, states = rnn(x_data)
    ```

  ![img](../resources/img/0603/img7.png)

  - input에서 shape([batch size], [sequance length], [input demension])

---

### Lab 12-1 many to one (word sentiment classification)

- many to one : 자연어 처리에서 많이 씀

  ![img](../resources/img/0603/img8.png)

  ![img](../resources/img/0603/img9.png)

![img](../resources/img/0603/img10.png)

- token을 integer로 맵핑하는 token dictionary
- 각각의 시퀀스의 길이가 다르기 때문에 ['<pad>']라는 헤더를 달아줌
- 딥러닝은 배치단위 연산이 효율적임
- 1 : 긍정, 0 : 부정

![img](../resources/img/0603/img11.png)

- max_sequence에 맞춰 '0'으로 padding 된 것을 확인 할 수 있음

![img](../resources/img/0603/img12.png)

- 전처리 : Embedding
  1. mask_zero : 전처리 단계에서 '0'으로 처리된 부분을 연산에서 제외
  2. trainable : one-hot 벡터를 트레이닝 하지 않음

- SimpleRNN : 기본적으로 시퀀스의 마지막 토큰을 받아, 처리한 결과 리턴
- Dense : RNN을 Dense로 활용하도록 함

![img](../resources/img/0603/img13.png)

- cross_entropy를 이용하여 loss를 계산함

![img](../resources/img/0603/img14.png)

- 성능 확인

  ![img](../resources/img/0603/img15.png)

---

### Lab 12-2 many to one stacking

- 











