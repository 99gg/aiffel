🔑 **PRT(Peer Review Template)**
## Reviewer: 윤소정<bt>
- [X]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 기능이 정상적으로 작동하는지?
        - 해당 조건을 만족하는 부분의 코드 및 결과물을 근거로 첨부
        - 1. CAM을 얻기 위한 기본모델의 구성과 학습이 정상 진행되었는가?	ResNet50 + GAP + DenseLayer 결합된 CAM 모델의 학습과정이 안정적으로 수렴하였다.<br>![image](https://github.com/99gg/aiffel/assets/104029654/6d2c819d-9ce6-4a6a-95ad-e33f70f336c0)<br>
              ![image](https://github.com/99gg/aiffel/assets/104029654/9d946dbb-a1a0-4efe-932c-6204800853ef)<br>
              ![image](https://github.com/99gg/aiffel/assets/104029654/91d10d3d-76c2-4e25-a5fa-cea6edba734b)<br>

          2. 분류근거를 설명 가능한 Class activation map을 얻을 수 있는가?	CAM 방식과 Grad-CAM 방식의 class activation map이 정상적으로 얻어지며, 시각화하였을 때 해당 object의 주요 특징 위치를 잘 반영한다.<br>![image](https://github.com/99gg/aiffel/assets/104029654/cb42f158-213c-4d1d-bb34-0b6b7b4e134e)
              ![image](https://github.com/99gg/aiffel/assets/104029654/a7e49541-95cb-4b78-9a44-fe14998c32a3)<br>

          3. 인식결과의 시각화 및 성능 분석을 적절히 수행하였는가?	CAM과 Grad-CAM 각각에 대해 원본이미지합성, 바운딩박스, IoU 계산 과정을 통해 CAM과 Grad-CAM의 object localization 성능이 비교분석되었다.
    <br> ![image](https://github.com/99gg/aiffel/assets/104029654/a543b2f7-d67a-4312-9f44-c3771fe8979b)<br>
![image](https://github.com/99gg/aiffel/assets/104029654/e27cd1cc-7a29-4fd6-8b29-bbbfceaa256d)<br>
![image](https://github.com/99gg/aiffel/assets/104029654/7d0775e6-fe0c-47c1-a3e5-f69ec065ce18)<br>
![image](https://github.com/99gg/aiffel/assets/104029654/6a9520b7-1591-46e4-9639-6c74b7d7a5c8)<br>

- [X]  **2. 핵심적이거나 복잡하고 이해하기 어려운 부분에 작성된 설명을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation/markdown이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 잘 작성되었다고 생각되는 부분을 근거로 첨부합니다.
        - ![image](https://github.com/99gg/aiffel/assets/104029654/235fab9a-23d9-417b-96ab-07a114e711b7)<br>
          해당 코드가 무슨 코드인지 주석이 적혀있습니다.

      
- [X]  **3.** 에러가 난 부분을 디버깅하여 “문제를 해결한 기록”을 남겼나요? 또는
   “새로운 시도 및 추가 실험”을 해봤나요? ****
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인 또는
    - 문제에서 요구하는 조건에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 근거로 첨부합니다.
      ![image](https://github.com/99gg/aiffel/assets/104029654/4f08081a-b079-492c-b502-e07bc40a93b6)<br>
      cam 이미지와 일반 이미지가 얼룩진 것처럼 블렌딩되어 음수 부분을 relu처리해서 블렌딩을 해주셨다는 점이 인상적이었습니다.

        
- [X]  **4. 회고를 잘 작성했나요?**
    - 프로젝트 결과물에 대해 배운점과 아쉬운점, 느낀점 등이 상세히 기록 되어 있나요?
    - ![image](https://github.com/99gg/aiffel/assets/104029654/9beaeb76-070a-4dbe-910c-90c9e0953b80)
    - 회고를 너무나도 잘 작성해주셔서 제 스스로를 반성하게되었습니다. 알아낸점과 모호한 점에서 배웠던 부분을 명료하게 적어주셔서 저도 읽으면서 다시 정리할 수 있어서 너무 좋았습니다.


- [X]  **5. 코드가 간결하고 효율적인가요?**
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 모듈화(함수화) 했는지
        - 잘 작성되었다고 생각되는 부분을 근거로 첨부합니다.
![image](https://github.com/99gg/aiffel/assets/104029654/7cb808b0-3e3c-4ccc-a321-b9fa578c0c0a)<br>
반복구문을 사용하여 사진들을 한 칸에서 다 보여줄 수 있게 해주었습니다.

__________________________________________________________________________________________
### 리뷰어 느낀점<br>
특히 grad cam에서 각 블락마다 이미지를 분석해주신것이 너무 인상깊었습니다. 이미지 블렌딩에서 이미지가 조금씩 깨져서 나오는 것에 대해서 저는 전혀 신경을 쓰지 않았었는데 그 부분이 문제가 되는 것을 발견하시고 그 부분에 대한 코드를 작성한 것에 대해 배우게됐습니다. 
또한 종민님의 회고를 보며 회고를 쓰므로써 배웠던 내용을 정리할 수 있구나를 깨달았습니다. 종민님 프로젝트를 리뷰하게되어 배울수 있었던게 참 많아 저에게는 매우 가치있었습니다. 감사합니다!

