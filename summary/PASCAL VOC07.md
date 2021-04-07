## 데이터 설명
PASCAL VOC는 Pattern Analysis, Statistical modeling and ComputAtional Learning Visual Object Classes의 약자로 classifcation, object detection, segmentation 성능을 평가할 수 있는 데이터셋이 포함되어 있다.


## 양
9,963개의 시퀀스(sequence)의 학습 데이터로 구성되어 있다. train 데이터 2,50개, validation 데이터 2,501개, test 데이터 4,952개로 구성되어 있다. 총 24,640개의 주석이 달린 개체가 있다.


## 클래스
사람, 동물(새, 고양이, 소, 개, 말, 양), 운송체(비행기, 자전거, 보트, 버스, 승용차, 오토바이, 기차), 사물(병, 의자, 식탁, 화초, 소파, 모니터) 총 20개의 클래스로 나누어져 있다.


##세부요소 (Feature)


```
FeaturesDict({
    'image': Image(shape=(None, None, 3), dtype=tf.uint8),
    'image/filename': Text(shape=(), dtype=tf.string),
    'labels': Sequence(ClassLabel(shape=(), dtype=tf.int64, num_classes=20)),
    'labels_no_difficult': Sequence(ClassLabel(shape=(), dtype=tf.int64, num_classes=20)),
    'objects': Sequence({
        'bbox': BBoxFeature(shape=(4,), dtype=tf.float32),
        'is_difficult': tf.bool,
        'is_truncated': tf.bool,
        'label': ClassLabel(shape=(), dtype=tf.int64, num_classes=20),
        'pose': ClassLabel(shape=(), dtype=tf.int64, num_classes=5),
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
image classification, object detection, segmentation 평가 알고리즘을 구축하고 평가하는데 유용하게 사용된다. 
Pascal VOC challenge는 2005년 부터 2012년까지 매년 진행되기도 하였으며 입력 영상에서 특정 종류의 물체를 검출해내는 성능을 겨루는 대회였다. 
물체 탐지 기술로서 대표적인 방법들이 이 대회에서 많이 탄생하였다. 
센서의 실시간성 저하로 인한 객체 검출의 지연은 자율주행자동차의 안전성에 큰 위험원이 될 수 있다. 
카메라를 이용한 딥러닝 기반 후, 측방 객체 검출과 차로 변경에 대해 딥러닝 알고리즘을 개발하고 객체 검출의 정확성과 실시간성을 VOC 데이터를 이용해 검증하는 등 단순한 객체 검출을 위한 데이터셋으로 사용될 뿐 아니라 안전한 자율주행 기술의 성능을 평가하는데에도 사용된다.  
