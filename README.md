# yolov8_yolov11_guide

#  YOLOv11 정리 (for Beginners)

>  이 문서는 YOLOv11을 공부하면서 정리한 내용입니다.  
> YOLOv8과의 비교, 주요 용어 정리, 설치 및 사용법을 담고 있습니다.

---

##  YOLO란?

**YOLO (You Only Look Once)** 는 객체 탐지(Object Detection)를 위한 딥러닝 모델입니다.  
이미지를 한 번만 보는(One Forward Pass) 방식으로 빠르고 정확하게 객체를 인식할 수 있습니다.

---

##  YOLOv11 개요

YOLOv11은 **Ultralytics**에서 공개한 YOLO 시리즈의 최신 버전으로,  
YOLOv8 이후의 향상된 성능과 효율을 제공합니다.  
특히 **추론 속도**, **정확도**, **경량화 모델 지원**에서 개선되었습니다.

---

##  YOLOv8 vs YOLOv11 비교표

| 비교 항목 | YOLOv8 | YOLOv11 |
|:-----------|:--------|:--------|
| **출시 시기** | 2023년 1월 | 2025년 10월 (예상) |
| **개발사** | Ultralytics | Ultralytics |
| **백본(Backbone)** | CSPDarknet + C2f 구조 | 개선된 C3k2 구조 + Dynamic Head |
| **모델 크기** | n, s, m, l, x | n, s, m, l, x (동일) |
| **정확도 (mAP)** | 약 53~56% (COCO 기준) | 약 57~60% (COCO 기준) |
| **추론 속도** | 빠름 | 더 빠름 (최대 30% 개선) |
| **학습 효율** | 좋음 | 향상됨 (적은 데이터로도 학습 가능) |
| **지원 태스크** | Detection, Segmentation, Pose, Classification | 동일 + 개선된 Tracking 지원 |
| **기타 특징** | AutoShape, Task 모듈화 | Dynamic Task Routing, 더 나은 Quantization 지원 |

>  YOLOv11은 **경량화 + 고성능**을 동시에 달성하도록 설계된 모델입니다.

---

##  YOLO 주요 용어 정리

| 용어 | 설명 |
|:-----|:------|
| **Bounding Box (BBox)** | 탐지된 객체를 둘러싸는 사각형 영역 |
| **Confidence Score** | 모델이 해당 객체가 존재한다고 확신하는 정도 (0~1) |
| **IoU (Intersection over Union)** | 예측 박스와 실제 박스가 얼마나 겹치는지 측정하는 지표 |
| **mAP (mean Average Precision)** | 탐지 성능의 종합적인 정확도 평가 지표 |
| **NMS (Non-Maximum Suppression)** | 겹치는 박스 중 가장 확률이 높은 박스만 남기는 과정 |
| **Anchor Box** | 다양한 크기의 객체 탐지를 위한 기준 박스 |
| **Backbone** | 특징(feature)을 추출하는 CNN 네트워크 부분 |
| **Neck** | Backbone의 특징을 통합해 탐지를 용이하게 만드는 구조 (예: FPN, PAN) |
| **Head** | 최종적으로 객체의 위치와 클래스를 예측하는 부분 |
| **Epoch** | 전체 학습 데이터셋을 한 번 학습하는 주기 |
| **Batch Size** | 한 번에 학습하는 데이터의 개수 |

---

##  설치 방법

```bash
# YOLOv11 설치 (Ultralytics 최신 버전)
pip install ultralytics
