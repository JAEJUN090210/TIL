- # TIL - 07.11 / DevOps - Kubernetes

  ## Summary

  - **Kubernetes(K8s)는 컨테이너화된 애플리케이션을 자동으로 배포, 관리, 확장하는 컨테이너 오케스트레이션 플랫폼**

  ------

  ## Body

  - **Kubernetes(K8s)**
    - 여러 서버에서 실행되는 **컨테이너를 효율적으로 관리**하는 오픈소스 플랫폼
    - 애플리케이션의 **배포, 확장(Scaling), 복구(Self-Healing)** 등을 자동화
  - **주요 구성 요소**
    - **Pod**
      - Kubernetes에서 컨테이너를 실행하는 가장 작은 단위
      - 하나 이상의 컨테이너를 포함할 수 있음
    - **Node**
      - Pod가 실행되는 서버(가상 머신 또는 물리 서버)
      - **Master(Control Plane)**와 **Worker Node**로 구성
    - **Deployment**
      - Pod의 개수와 상태를 관리
      - 장애 발생 시 새로운 Pod를 생성하여 원하는 상태를 유지
    - **Service**
      - Pod에 고정된 네트워크 주소를 제공
      - 여러 Pod로 트래픽을 분산(Load Balancing)
    - **Ingress**
      - 외부 사용자의 HTTP/HTTPS 요청을 클러스터 내부 서비스로 전달
      - 도메인 기반 라우팅과 SSL(TLS) 설정 가능
  - **일반적인 Kubernetes 동작 흐름**
    1. Docker 이미지 생성
    2. 이미지 레지스트리(Harbor, Docker Hub 등)에 업로드
    3. Deployment YAML 작성
    4. Kubernetes 클러스터에 배포
    5. Scheduler가 적절한 Node에 Pod 배치
    6. Service를 통해 Pod에 접근
    7. Ingress를 통해 외부에서 서비스 이용

  ------

  ## (+)

  - 컨테이너 자동 배포 및 관리
  - 장애 발생 시 자동 복구(Self-Healing)
  - 손쉬운 수평 확장(Scaling)
  - 무중단(Rolling Update) 배포 지원
  - 리소스 효율성 향상
  - 다양한 클라우드 및 온프레미스 환경에서 동일하게 운영 가능

  ------

  ## (-)

  - 학습 난이도가 높음
  - 초기 클러스터 구축 및 운영이 복잡함
  - 네트워크와 스토리지 설정이 까다로울 수 있음
  - 리소스 사용량이 단순 서버 운영보다 많음
  - 장애 발생 시 원인 분석이 어려울 수 있음