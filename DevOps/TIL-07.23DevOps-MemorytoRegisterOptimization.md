# TIL - 07.23 / DevOps - Memory to Register Optimization

## Summary

- **Memory to Register Optimization은 메모리에 저장된 값을 가능한 한 CPU 레지스터(Register)에 유지하여 메모리 접근을 줄이고 프로그램의 실행 성능을 향상시키는 최적화 기법**

------

## Body

- **Memory to Register Optimization**
  - 컴파일러가 메모리에 저장된 변수를 **CPU 레지스터로 승격(Promotion)**하여 사용하는 최적화 기법
  - 메모리 접근보다 훨씬 빠른 레지스터를 활용하여 실행 속도를 향상
  - LLVM의 **Mem2Reg** 패스가 대표적인 구현 예시
- **Memory to Register Optimization의 특징**
  - **Register Promotion**
    - 지역 변수를 메모리 대신 레지스터에서 관리
  - **Load/Store Elimination**
    - 불필요한 메모리 읽기와 쓰기를 제거
  - **SSA 변환**
    - 변수를 SSA 형태로 변환하여 최적화를 쉽게 수행

------

## (+)

- 메모리 접근 횟수를 크게 감소시킴
- 프로그램 실행 속도 향상
- CPU 캐시 의존도를 줄일 수 있음
- 불필요한 Load/Store 명령 제거
- 다른 컴파일러 최적화와 함께 높은 성능 향상 효과

------

## (-)

- 사용할 수 있는 레지스터 개수가 제한적임
- 변수 수가 많으면 Register Spill이 발생할 수 있음
- Spill이 발생하면 다시 메모리를 사용하여 성능이 저하될 수 있음
- 전역 변수나 포인터가 많은 코드는 최적화가 어려움
- 디버깅 시 변수 위치 추적이 복잡해질 수 있음