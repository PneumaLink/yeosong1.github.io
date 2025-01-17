# cub3d 구현 과정

## 배경 지식
- [Essence of linear algebra - 유튜브](https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=1)
  - *벡터에 대한 기본적인 이해. 벡터가 뭔지 모른다면 1,2,3강 2번씩 시청*
- [스프라이트란? - 위키피디아](https://en.wikipedia.org/wiki/Sprite_(computer_graphics))
  - 하드웨어에 의해 배경과 함께 합성 된 고정 된 크기의 개체.
  - 영상 속에 작은 2차원 비트맵이나 애니메이션을 합성하는 기술.
  - 다양한 층의 이미지, 텍스트 등을 각각의 우선순위를 두고 합성하는 기술을 통틀어 일컫는다.
  - *지도상의 확정된 어떤 위치에 고정되어있는 아이템 이미지 정도?*
- mihykim님의 [레이캐스팅 튜토리얼 (한글ver)](https://github.com/365kim/raycasting_tutorial).
  - *벡터를 볼 때마다 0,0 기준으로 어느 방향으로 뻗는지를 떠올릴 수 있다면* 
  - *벡터 덧셈 식을 볼 때마다 좌표평면 상에서 두 벡터를 더하는 그림을 떠올릴 수 있다면*
  - *[minckim님의 강의자료](https://42born2code.slack.com/archives/CU6MTFBNH/p1601382410192500)를 정독하셨다면*
  - 의외로? 술술 읽히는 듯
 
## 연습

### 🐣 빈 윈도우 띄워보기
- [MiniLibX 라이브러리 읽기](miniRT라이브러리)
- [간단한 파일 컴파일 해보기 - 빈 윈도우 띄워보기](miniRT창띄우기)
- [Makefile](miniRT-Makefile)

### 🐣 esc 종료(키 이벤트) 추가해보기 
- [맥 키코드](맥-키코드)
- [esc 종료 추가해보기](miniRT종료해보기)


### 🐣255,255,255 이렇게 들어온 색을 16진수 RGB형식으로

~~~
함수들은 int color를 받아쓰니까
(r * 256 * 256) + (g * 256) + b
// 결과적으로 16진수로 볼 때 rr0000 + gg00 + bb 가 되는 것임.
~~~


## 이해





---------

## 할 일.....

- 에러 케이스 정리, 에러 처리 함수 작성
- 카메라 전환
- 해상도 한계 설정
  - beta 버전 mlx에서 get_screen_size() 함수 사용











--------------------------
대충 내용 정리.....


맵에러

(아니면 에러처리)
1. [x] 맵 파일 이름이 “.cub”로 끝나는지를 확인 합니다
2. [x] 요소가 다 있는지(R, NO,SO,WE,EA,S,F,C) 확인합니다.
3. [x] 항상 맨밑에 있는 지도 외에, 나머지 요소들이 순서가 다르게 적혀있어도 파싱이 되는지 확인합니다.
4. [x] 지도 외에 나머지 요소들에서 하나 이상의 공백이 있어도 잘 처리되는지 확인합니다.


1. [x] 지도에 0, 1, 2, 플레이어 표시문자 이렇게 4가지의 문자로만 구성되어 있는지 확인합니다.
2. [x] 지도가 벽(1)으로 둘러쌓여있는지 여부를 확인 합니다.
3. [x] 지도 공백을 잘 처리하는지 확인합니다.
4. [ ] 플레이어가 맵 안에 있는지, 있다면 N/S/E/W 중 하나로 잘 표시되어있는지, 1명인지 확인합니다.
        
