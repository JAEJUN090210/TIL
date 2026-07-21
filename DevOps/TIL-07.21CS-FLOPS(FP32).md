# TIL - 07.21 / CS - FLOPS (FP32)

## Summary

- **FLOPS(Floating Point Operations Per Second)는 컴퓨터가 1초 동안 수행할 수 있는 부동소수점 연산의 횟수를 나타내는 성능 지표이며, FP32는 32비트 단정밀도 부동소수점 연산을 의미**

------

## Body

- **FLOPS (Floating Point Operations Per Second)**
  - 컴퓨터의 **부동소수점(Floating Point) 연산 성능**을 나타내는 단위
  - CPU, GPU, AI 가속기 등의 계산 능력을 비교할 때 사용
  - 숫자가 클수록 초당 더 많은 연산을 수행할 수 있음
- **FP32 (Single Precision Floating Point)**
  - IEEE 754 표준의 **32비트 부동소수점 형식**
  - 실수 연산의 정확도와 성능의 균형이 좋아 가장 널리 사용됨
  - 게임, 그래픽 처리, 과학 계산 등 다양한 분야에서 활용
- **주요 FLOPS 단위**
  - **KFLOPS**
    - 초당 1천(10³) 번의 연산
  - **MFLOPS**
    - 초당 100만(10⁶) 번의 연산
  - **GFLOPS**
    - 초당 10억(10⁹) 번의 연산
  - **TFLOPS**
    - 초당 1조(10¹²) 번의 연산
  - **PFLOPS**
    - 초당 1천조(10¹⁵) 번의 연산
  - **EFLOPS**
    - 초당 100경(10¹⁸) 번의 연산
- **FP32 FLOPS에 영향을 주는 요소**
  - GPU 또는 CPU의 연산 유닛(Core) 수
  - 동작 클럭(Clock Frequency)
  - 명령어 집합(AVX, CUDA, Tensor Core 등)
  - 메모리 대역폭(Bandwidth)
  - 병렬 처리 성능

------

## (+)

- CPU와 GPU의 연산 성능을 비교하기 쉬움
- 하드웨어의 이론적인 계산 능력을 확인 가능
- 다양한 성능 단위(GFLOPS, TFLOPS 등)로 표현 가능
- 벤치마크 및 하드웨어 비교에 널리 사용됨

------

## (-)

- 실제 애플리케이션 성능과 항상 일치하지 않음
- 메모리 대역폭과 I/O 성능은 반영하지 않음
- CPU와 GPU의 FLOPS를 단순 비교하기 어려움
- 동일한 FLOPS라도 아키텍처에 따라 성능 차이가 발생