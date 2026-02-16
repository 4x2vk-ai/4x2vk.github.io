---
layout: post
title: "[Docker] Docker 설치 완벽 가이드"
date: 2026-02-16 10:00:00 +0900
description: Docker 설치 과정을 단계별로 안내하는 완벽 가이드입니다. 윈도우, WSL2, 우분투, 맥OS 모든 환경을 지원합니다.
image: /assets/img/content/2025-07-31/image.png
categories: [TIL]
tags: [docker, installation, wsl, ubuntu, macos, windows]
---

## 서론

도커(Docker)는 개발 환경을 구성하는 필수적인 도구입니다. 윈도우, WSL2, 우분투, 맥OS 등 다양한 환경에서 Docker를 설치하는 방법을 정리했습니다.

이 가이드를 따르 하면 다음과 같이 할 수 있습니다:

✅ 윈도우 환경에서 Docker 설치
✅ WSL2를 통한 리눅스 환경 설정
✅ 우분투 서버에 Docker 설치
✅ 맥OS에서 Docker 사용

Docker는 개발 환경을 표준화하고 일관성을 유지하는 강력한 도구입니다. 설치 후 다양한 프로젝트에서 사용해 보세요!

## 목차

1. [Windows](#windows)
2. [WSL2](#wsl2)
3. [Ubuntu 22.04](#ubuntu-2204)
4. [macOS](#macos)

---

## Windows

### WSL2 설치를 위한 사전 준비

Windows 설정 앱 → 제어판 → 프로그램 및 기능 → Windows 기능 켜기/끄기 → Linux용 Windows 하위 시스템

---

## WSL2

WSL2 환경에서는 Windows Docker Desktop의 WSL 통합 기능을 사용하는 것이 가장 편리합니다.

---

## Ubuntu 22.04

위의 [Windows](#windows) 섹션의 Ubuntu 22.04 설치 과정을 참고하세요.

---

## macOS

### Homebrew를 이용한 Docker, Docker Compose 설치

[https://brew.sh/ko](https://brew.sh/ko)

```bash
# 사전에 homebrew 설치 필요
# 커맨드 복사 및 붙여넣기
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### 커맨드 복사 및 붙여넣기

```bash
# docker for mac설치
brew install docker

# docker compose 설치
brew install docker-compose
```

### 버전 확인

```bash
# docker version 확인
docker --version

# docker compose version 확인
docker-compose --version
```

### macOS 특정 도구

https://subicura.com/mac/dev/apple-silicon.html#command-line-tools

### Docker 공식 사이트에서 Docker Desktop 다운로드 및 설치

https://docs.docker.com/desktop/setup/install/mac-install/

---

## 설치 완료 후 확인

### Docker 실행 테스트

```bash
# hello world 컨테이너 실행
docker run hello-world

# 현재 실행 중인 컨테이너 확인
docker ps

# Docker 시스템 정보 확인
docker info
```

### Docker Compose 테스트

```bash
# docker-compose.yml 생성
echo 'version: "3.8"
services:
  web:
    image: nginx:latest
    ports:
      - "80:80"' > docker-compose.yml

# 서비스 시작
docker-compose up -d
```

---

## 문제 해결

### WSL2에서 Docker가 실행되지 않을 때

```bash
# WSL2 버전 확인
wsl --version

# Docker Desktop 설정 확인
# Windows Docker Desktop → Settings → WSL Integration
```

### Linux에서 권한 문제

```bash
# docker 그룹에 사용자 추가
sudo usermod -aG $USER docker

# sudo 없이 docker 실행
newgrp docker
```

### macOS에서 M1/M2 칩셋 아키텍처 문제

```bash
# Apple 실리콘용 Docker Desktop 설치
# 일반 intel 버전 대신 Apple Silicon 버전 사용
```

---

## 참고 자료

- [Docker 공식 문서](https://docs.docker.com/)
- [Docker Compose 문서](https://docs.docker.com/compose/)
- [WSL2 문서](https://docs.microsoft.com/en-us/windows/wsl/about)
- [Homebrew 문서](https://docs.brew.sh/)

---

## 결론

이 가이드를 따르면 다음과 같이 할 수 있습니다:

✅ 윈도우 환경에서 Docker 설치
✅ WSL2를 통한 리눅스 환경 설정
✅ 우분투 서버에 Docker 설치
✅ 맥OS에서 Docker 사용

Docker는 개발 환경을 표준화하고 일관성을 유지하는 강력한 도구입니다. 설치 후 다양한 프로젝트에서 사용해 보세요!
