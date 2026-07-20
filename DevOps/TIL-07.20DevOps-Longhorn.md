# TIL - 07.20 / DevOps - Longhorn

## Summary

- **Longhorn은 Kubernetes 환경에서 영구 스토리지(Persistent Storage)를 제공하는 오픈소스 분산 블록 스토리지 시스템**

------

## Body

- **Longhorn**
  - Kubernetes 클러스터에서 **영구 볼륨(Persistent Volume)**을 제공하는 CNCF 오픈소스 프로젝트
  - 여러 Worker Node에 데이터를 복제하여 **고가용성(High Availability)**과 **데이터 안정성**을 보장
  - CSI(Container Storage Interface)를 지원하여 Kubernetes와 쉽게 연동 가능
- **주요 기능**
  - **Persistent Volume(PV) 제공**
    - Pod가 재시작되어도 데이터를 유지
    - Kubernetes의 PVC를 통해 자동으로 볼륨 생성
  - **Data Replication**
    - 데이터를 여러 Node에 복제
    - Node 장애 발생 시 다른 Replica를 이용하여 서비스 지속
  - **Snapshot**
    - 특정 시점의 데이터를 저장
    - 장애 발생 시 원하는 시점으로 복구 가능
  - **Backup & Restore**
    - S3, NFS 등의 외부 저장소에 백업 가능
    - 백업 데이터를 이용하여 손쉽게 복원 가능
  - **Volume Expansion**
    - 서비스 중단 없이 볼륨 크기 확장 가능

------

## (+)

- 데이터를 여러 Node에 복제하여 높은 가용성 제공
- Snapshot 및 Backup 기능 기본 제공
- 서비스 중단 없이 볼륨 확장 가능
- 별도의 외부 스토리지 장비 없이 구축 가능
- Web UI를 통해 스토리지 상태를 쉽게 관리 가능

------

## (-)

- Replica 수만큼 디스크 용량이 추가로 필요
- 디스크 및 네트워크 사용량이 증가할 수 있음
- 소규모 클러스터에서는 리소스 오버헤드가 발생
- 로컬 디스크 성능과 네트워크 품질에 영향을 많이 받음
- Replica가 부족한 경우 장애 발생 시 데이터 손실 위험이 증가할 수 있음