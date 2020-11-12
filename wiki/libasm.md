# libasm


- 서브젝트 [libasm.en.subject.pdf](https://github.com/yeosong1/yeosong1.github.io/files/5485720/en.subject.2.pdf)

## 일반 지침에 따른 배경지식 정리

- [x] 64bit ASM 을 써야합니다. (호출 규약 calling convention 주의)
  - [호출 규약](https://ko.wikipedia.org/wiki/%ED%98%B8%EC%B6%9C_%EA%B7%9C%EC%95%BD)? 코드가 호출자(caller)로부터 변수를 받고, 어떻게 결과를 반환하는지에 대한 규약. 
  - 리눅스는 64비트 모드에서 정수 타입의 파라미터 전달시, 순서대로 RDI, RSI, RDX, RCX, R8, R9까지 6개의 레지스터를 사용하고 7개 이상이면 스택을 통해 전달합니다.
    - 32비트에서는 레지스터 이름들이 E로 시작한다. EDI, ESI, EDX ... 16bit, 8bit.. 등 비트별로 다르다.
  - 실수 타입의 파라미터의 경우는 XMM0 ~ XMM7까지 8개를 순서대로 사용하고 그 이상이면 스택으로 전달합니다.
  - [64비트 리눅스 vs 64비트 윈도우 호출 규약 비교(Calling Convention)](https://kkamagui.tistory.com/811)

- [x] .s (O) / inline ASM(X)
  - *.s 는 어셈블리 코드의 확장자이다. [출처: 블로그 C언어 강좌 1편](https://blog.hexabrain.net/2)
  - inline 어셈블리는 C 소스 코드의 중간에 어셈블리 명령어를 추가하는 관행이다. - [출처: SO documentation](https://sodocumentation.net/ko/c/topic/4263/%EC%9D%B8%EB%9D%BC%EC%9D%B8-%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC)
- [x] nasm으로 컴파일해야 합니다.
  - brew 설치(클러스터 맥에): `curl -fsSL https://rawgit.com/kube/42homebrew/master/install.sh | zsh`
  - nasm 설치: `brew install nasm`
  - 터미널에 `nasm -h` 해서 사용법을 확인하자: 우리의 환경에 따르면 `nasm -f macho64 *.s`
- [x] 문법: Intel(O) / AT&T(X)
  - 어셈블리 컴파일러 = `어셈블러`
    - `컴파일러`: 소스를 특정 컴퓨터 아키텍쳐에 맞는 기계어 코드로 바꾸어 주는 프로그램
  - 어셈블러 종류에 따라 채택 가능한 문법이 다르다.
    - GAS(GNU Assembler) - AT&T 문법
    - NASM(Netwide Assembler) - Intel 문법
    - MASM(Microsoft Macro Assembler) - Intel 문법 등.. 이외에도 어셈블러는 여러가지 종류가 있다.

- [x] 평가 항목은 아니지만, 동료평가시 테스트를 편하게 만들어주는 테스트 프로그램을 만들기를 권장합니다.
- [x] 할당된 깃 레포에 과제 제출 하세요. Deepthought의 채점 중 작업 섹션에서 오류가 발생하면 평가가 중지됩니다.

### 어셈블리 기초 명령 정리

출처: [Paul A. Carter의 [PC 어셈블리어]에서 1.3.4](https://pacman128.github.io/static/pcasm-book-korean.pdf)

| 명령어 | 수행 내용 |
| --- | --- |
| mov | `dest, src` |
| add | |
| sub | |
| inc | |
| dec | |








## 체크리스트

### Makefile 체크리스트

- [x] $(NAME) (= libasm.a)
- [x] all
- [x] clean
- [x] fclean
- [x] 불필요한 리컴파일, 리링크 없어야 함.

### 필수 작성 및 체크리스트

- [ ] strlen
- [ ] strcpy
- [ ] strcmp
- [ ] write
- [ ] read
- [ ] strdup

- [ ] 시스템콜syscall 하는 중에 에러 있는지 체크
- [ ] 변수 errno 세팅 (extern ___error 사용 가능)

### 최종 점검

- [ ] segmentation fault
- [ ] bus error
- [ ] double free
- [ ] 가독성

### 보너스 작성

- [ ] atoi_base
- [ ] list_push_front
- [ ] list_size
- [ ] list_sort
- [ ] list_remove_if

### 보너스 최종 점검

- [ ] rule bonus
- [ ] _bonus.c / _bonus.h
- [ ] segmentation fault
- [ ] bus error
- [ ] double free
- [ ] 가독성


