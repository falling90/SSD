# SSD (Single Shot MultiBox Detector)
    
    -. 테두리 상자 조정을 위해 Feature을 재추출하지 않음
    -. 속도와 정확성의 Trade-off 문제를 극복하고자 고안됨
    -. 분류와 조정을 같이 실행하는 단일 신경망 모델
   
>**등장 배경**

<img src="https://github.com/falling90/SSD/blob/main/Reference/Image/1.PNG" width="600px" height="300px"></img><br/>  

    -. Object Detection 은 최근 자율주행 등에 활용되면서 정확도 뿐만 아니라 신속성도 중요해짐
    -. R-CNN 계열 모델은 정확성은 있으나 신속성이 떨어져 이를 개선하고자 등장


## SSD 구조 및 절차
>**Model**

<img src="https://github.com/falling90/SSD/blob/main/Reference/Image/2.PNG" width="1000px" height="300px"></img><br/>  

>**특징**

<img src="https://github.com/falling90/SSD/blob/main/Reference/Image/3.PNG" width="1000px" height="300px"></img><br/>  

    1. 이미지 개념적 축소 & Bounding Box 설정
      -. 연속적 특징 추출 시 Feature Map Size가 작아지는 특성을 활용.
      -. Bounding Box의 Size 및 Ratio을 Grid 기반으로 설정
      
<img src="https://github.com/falling90/SSD/blob/main/Reference/Image/4.PNG" width="1000px" height="500px"></img><br/>  


>**Loss 계산**

<img src="https://github.com/falling90/SSD/blob/main/Reference/Image/5.PNG" width="1000px" height="500px"></img><br/>  

    -. 


>**NMS**

<img src="https://github.com/falling90/SSD/blob/main/Reference/Image/6.PNG" width="1000px" height="300px"></img><br/>  

    -. NMS : Not Maximum Suppression
    -. 일정 Threshold 기준으로 중요하지 않은 Data 제거 및 Data 처리
    -. 잔여 Bounding Box 끼리의 IOU 계산 후 특정 기준 넘으면 제거 (동일 Object 로 인식)
