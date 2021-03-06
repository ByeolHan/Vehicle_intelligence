## 데이터 설명
BDD100K는 ‘Berkeley Deep Drive’의 약자로 40초의 비디오 시퀀스, 720픽셀 해상도, 초당 30프레임 고화질로 취득된 10만개의 비디오 시퀀스로 구성된다. 거친 주행 환경 구현, GPS 정보, IMU 데이터 및 타임 스탬프가 포함되어 있다. 녹화된 비디오는 비 내리는 날씨, 흐린 날씨, 맑은 날씨, 안개와 같은 다양한 날씨 조건이 기록되어 있다. 데이터 세트는 낮과 밤이 적절한 비율로 기록되어 있다. image tagging(이미지 태그 지정), lane detection(차선 감지), drivable area segmentation(주행영역 분할), object detection(객체 감지), semantic segmentation(이미지 분할), instance segmentation(인스턴스 분할), multi-object detection tracking(다중 객체 감지 추적), multi-object segmentation tracking(다중 객체 분할 추적), domain adaptation(도메인 적응), imitation learning(모방 학습) 총 10가지 작업으로 구성된다.이미지에 쉽게 주석 처리하기 위해 수직 차선은 적색, 평행 차선은 청색으로 구분하였다. 적색 표시 있는 운전 경로와 청색 표시가 있는 대안 운전 경로로 주행 가능 구역을 구분한다. 차선 구분을 위한 데이터는 쉽게 주석처리하기 위해 수직 차선은 적색, 평행 차선은 청색으로 구분하였다. 도로 객체 탐지 데이터셋은 100,000개의 이미지에 주석이 달린 2D Bounding Box가 포함되어 있다. 


## 양
주석 처리된 10만개 이상의 다양한 비디오 클립에 주행 장면의 가장 큰 데이터셋을 수집하고 주석을 달았다.


## 클래스
pedestrian, rider, other person, car, bus, truck, train, trailer, other vehicle, motorcycle, bicycle의 클래스로 이루어져 있다.
주행 영역 분류를 위해 70,000개 훈련용, 10,000개 검증용 픽셀맵 파일도 제공한다. 객체 분류은 7,000개 훈련용 데이터셋과 1,000개의 검증용 데이터셋을 제공하고 있다.


## 활용 예
도로/ 포장도로의 보행자 탐지의 컴퓨터 비전 알고리즘 구현에 유용하며 보행자 뿐만 아니라 도로 객체 감지, 객체 분류, 차선 구분 등의 머신러닝 학습, 시뮬레이션에  사용될 수 있다. 눈, 비, 흐림 등 다양한 날씨를 포함하고, 야간과 터널 등 조도가 낮은 상황에서도 수집이 됐기 때문에 객체 인지 모델을 일반화가 가능하도록 학습시키는 것이 가능하다. 다양한 상황에서 객체를 정확하게 인식하여 자율주행의 기술의 정확성, 안전성을 높일 수 있다.
    
