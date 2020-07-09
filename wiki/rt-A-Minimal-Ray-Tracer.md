# A Minimal Ray-Tracer: Rendering Simple Shapes (Sphere, Cube, Disk, Plane, etc.)

Contents
- Parametric and Implicit Surfaces
- 광선-구 교차
- 미니멀 레이 트레이서: 렌더링 영역
- Ray-Plane과 Ray-Disk 교차
- Ray-Box 교차
- 소스 코드

*Keywords: ray-tracing, geometry, sphere, plane, disk, cube, parametric surface, implicit surface, ray-geometry intersection.레이 트레이싱, 기하학, 구, 평면, 원판, 정육면체, 파라메트릭 표면, 임플리시트 표면, 광선-기하 교차*

## 소개
이전 레슨에서는 primary rays를 생성하는 방법을 배웠지만 아직 이미지를 생성할 수는 없었습니다.
왜냐면 primary rays와 기하(어떤 종류든)의 교차를 계산하는 법을 안배웠기 때문입니다.
이번 레슨에서는 구처럼 간단한 모양의 기하로 광선-기하 교차 계산에 대해 알아 봅니다.
구체는 광선 추적 하기가 쉽기 때문에 레이 트레이서를 프로그래밍하는 방법을 배우는 사람들이 자주 사용합니다.
이 수업은 주제가 약간 일치하지 않습니다:

- 1 장(이번 장)에서는 parametric 표면과 implicit 표면에 대해 알아 봅니다. 이러한 표면이나 모양은 수학적으로 정의될 수 있다는 점에서 특별합니다. 이것은 다음 장에서 광선에 대한 교차점을 계산하기 위해 공부할 기술의 기초입니다.
- 2 장에서는 광선과 구의 교차점을 계산하는 몇 가지 기술에 대해 알아 봅니다.
- 3 장에서는 우리가 앞 레슨에서 배운 primary rays 생성, primary rays가 장면을 구성하는 구와 교차하는지 계산하기 위해 이 레슨의 2장에서 배운 내용을 함께 정리합니다. 이 레슨을 위해 개발할 프로그램은 최소한이지만 기능적인 레이 트레이서의 기초를 형성합니다. `trace()` 함수에 대해 배웁니다. 여기서 우리는 primary rays에 대해 각 구를 테스트하고 교차 거리와 가장 가까운 교차 구에 대한 포인터를 반환합니다 (선이 구와 전혀 교차하지 않은 경우). `castRay()` 함수에서 교차점에서 법선 좌표와 텍스처 좌표를 사용하여 간단한 음영 처리 방법을 배웁니다.
- 마지막으로 4 장과 5 장에서는 평면, 디스크, axis aligned boxes처럼 다른 간단한 모양으로 광선의 교차점을 계산하는 다양한 기술에 대해 학습합니다.
- 평소와 같이 이 단원의 마지막 장에는 예제 프로그램의 전체 소스 코드가 포함되어 있습니다.

## 광선-기하 교차