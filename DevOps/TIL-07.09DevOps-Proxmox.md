# TIL - 07.09 / DevOps - Proxmox

## Summary

- **Proxmox VE(Proxmox Virtual Environment)는 KVM과 LXC를 기반으로 하는 오픈소스 Hypervisor 운영체제이다.**

------

## Body

- **KVM(Kernel-based Virtual Machine)**

  - 완전 가상화(Full Virtualization) 제공
  - Windows, Linux 등 다양한 운영체제를 VM으로 실행 가능

- **LXC(Linux Containers)**

  - 운영체제 커널을 공유하는 컨테이너 방식
  - VM보다 가볍고 빠르며 자원 사용량이 적음

- **Web GUI**

  - 브라우저에서 서버 관리 가능
  - VM/LXC 생성, 삭제, 백업, 모니터링 등을 GUI로 수행

- **Storage**

  - Local Storage
  - NFS
  - iSCSI
  - Ceph
  - ZFS 등 다양한 스토리지 지원

- **Networking**

  - Linux Bridge
  - VLAN
  - Bonding(LACP)
  - SDN 기능 지원

  ------

  ## (+)

  - Hypervisor는 하나의 물리 서버에서 여러 개의 가상 컴퓨터를 실행할 수 있도록 하는 가상화 기술이다.
  - VM은 높은 호환성과 격리성을 제공하지만 리소스 사용량이 크고, LXC는 빠르고 가볍지만 Linux 환경에서만 사용할 수 있다.
  - Proxmox는 오픈소스임에도 Enterprise 수준의 기능(Cluster, HA, Live Migration, Backup 등)을 대부분 제공한다.
  - 웹 브라우저만으로 대부분의 관리 작업을 수행할 수 있어 CLI 사용을 최소화할 수 있다.

  ------

  ## (-)

  - Windows VM은 LXC가 아닌 KVM 기반 VM에서만 실행할 수 있다.
  - HA, Live Migration 등 일부 기능은 여러 대의 Proxmox 노드로 클러스터를 구성해야 사용할 수 있다.
  - LXC는 호스트 커널을 공유하므로 커널 수준 기능이 필요한 일부 애플리케이션에는 적합하지 않을 수 있다.