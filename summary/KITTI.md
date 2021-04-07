## 데이터 설명
KITTI Dataset은 RGB 카메라와 벨로다인 라이다(Velodyne Lidar) 등의 센서가 장착된 차량으로 독일 도시 지역에서 추출되었다. 데이터 셋은 난이도에 따라 easy, moderate, hard로 나누어진다. 전체 데이터 셋은 stereo, sceneflow, depth, obejct, tracking 등 많은 작업물이 포함되어있다. 

## 양
7,481개의 시퀀스(sequence)의 학습 데이터로 구성되어 있다. train 데이터 6,347개, validation 데이터 423개, test 데이터 711개로 구성되어 있다.

## 클래스
학습 데이터는 9가지 객체의 종류(Car, Van, Truck, Pedestrian, Person_sitting, Cyclist, Tram, Misc, DontCare)와 51,867개의 라벨을 포함하고 있다.


##세부요소 (Feature)


```
FeaturesDict({
    'image': Image(shape=(None, None, 3), dtype=tf.uint8),
    'image/file_name': Text(shape=(), dtype=tf.string),
    'objects': Sequence({
        'alpha': tf.float32,
        'bbox': BBoxFeature(shape=(4,), dtype=tf.float32),
        'dimensions': Tensor(shape=(3,), dtype=tf.float32),
        'location': Tensor(shape=(3,), dtype=tf.float32),
        'occluded': ClassLabel(shape=(), dtype=tf.int64, num_classes=4),
        'rotation_y': tf.float32,
        'truncated': tf.float32,
        'type': ClassLabel(shape=(), dtype=tf.int64, num_classes=8),
    }),
})
```
- image: 문장 단위 이미지 설명
- image/filename : 파일 이름
- name : class 이름 설명
- bbox : xmin, ymin, xmax, ymax 위치(float32 type)
- difficult, truncated 0,1 Bool 값으로 설명한다.
- label : 클래스 이름 설명
- pose : 객체 위치 설명 eg)right

## 활용 예
딥러닝에 기반한 거리측정, 객체 탐지 기술, slam 알고리즘 모델의 학습데이터로 많이 사용되며 모델의 성능을 검증하는데에도 쓰인다. slam 기술이 상용화 될 경우
주변 환경과 주변 차량을 인식하여 정밀한 인식이 가능하고 자율주행 기술이 상용화 되기 이전에도 현재 차량 환경에서 운전자의 안전을 크게 높일 수 있다.
현실에서 수집된 공개 데이터셋은 특정한 나라의 교통 상황에만 국한되어 있고, 사계 변화가 뚜렷한 국내 사정에 적합하지 못한다는 단점이 있다. 또한 데이터가 모델 학습에 사용되려면 정답 데이터인 라벨도 필수적으로 확보가 되어야한다. 많은 데이터를 수집하고 데이터에 라벨을 수작업으로 붙이는 것은 많은 시간과 비용이 들어가며 인적요인으로 잘못 지정될 수 있다는 문제점 또한 있다. 네이버 랩스에서는 이러한 문제점들을 보완하기 위해 Virtual KITTI라는 가상의 데이터셋을 생성하고 발표하였다. 시뮬레이션 플랫폼에서는 악천우의 제약없이 국내 도로환경의 데이터 구현이 가능하다. 네이버 랩스에서는 유니티 게임 엔진을 사용하여 KITTI 데이터셋을 재현했다. 기계학습 모델을 이용하여 교육, 테스하기 위한 최초의 합성 데이터셋 중 하나이다. 가상 KITTI에는 다양한 이미징 및 기상 조건에서 도시환경의 5가지 가상세계에서 생성된 50 개의 고해상도 단안 동영상 (21,260 프레임)이 포함되어 있다. 현재 Virutal KITTI.ver2까지 출시되었다. 합성 데이터셋이 실제 데이터셋을 완전히 대체할 수는 없지만 예비 프로토타입을 평가하는데 유용한 것으로 입증됐으며, 실제 데이터셋과 함께 사용하면 성능을 개선할 수 있다.      


