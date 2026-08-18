<div align="center">

  <!-- PIKONE 로고 이미지 업로드 후 src 교체 -->

  <!-- <img src="PIKONE_LOGO_IMAGE_URL" width="197" /> -->

  <h3 align="center">PIKONE 🍽️</h3>

  <p align="center">
    사진으로 기록하는 나만의 외식 일기장<br>
    <a href="https://github.com/TmPIKONE/backend-master"><strong>Backend Repo »</strong></a><br>
    <a href="https://github.com/TmPIKONE/pikone-frontend"><strong>Frontend Repo »</strong></a>
  </p>

</div>

<br>

<details open>
  <summary><strong>&nbsp;📖&nbsp;목차</strong></summary>

1.   [🔍 Introduction](#-introduction)
2.   [📄 Documents](#-documents)
3.   [📹 Demo](#-demo)
4.   [💡 Tech Stack](#-tech-stack)
5.   [🗂️ Database](#️-database)
6.   [💻 Architecture](#-architecture)

   *  [System](#system)
   *  [Record Pipeline](#record-pipeline)
   *  [Recommendation](#recommendation)
7.   [📂 Directory Structure](#-directory-structure)
8.   [👨‍💻 Developer](#-developer)

</details>

<br>

---

## 🔍 Introduction

### 배경

방문했던 식당이 마음에 들었어도 시간이 지나면 **어디에서 무엇을 먹었는지 기억하기 어렵습니다.**
사진은 갤러리에 남지만, 식당·날짜·함께한 사람·다시 방문하고 싶은지와 같은 외식 경험은 서로 흩어져 있습니다.

또한 기존 맛집 서비스의 추천은 다른 사람들의 리뷰와 인기 순위에 집중되어 있어,
**내가 실제로 방문했던 식당과 나의 취향을 기반으로 다음 식당을 찾기는 어렵습니다.**

그래서 질문했습니다.

**"내가 먹었던 경험 자체를 기록하면, 그 기록이 다음 식당을 고르는 기준이 될 수 있지 않을까?"**

PIKONE은 사진을 중심으로 외식 경험을 간편하게 기록하고,
누적된 방문 기록과 취향을 기반으로 다음 식당까지 추천하는 **개인 외식 기록 서비스**입니다.

### 특징

* 사진 기록 :  음식 사진을 중심으로 방문했던 외식 경험 기록
* 자동 기록 보조 :  사진의 EXIF·이미지 분석을 활용하여 기록 작성 과정 보조
* 식당 연결 :  장소 검색 API를 활용해 실제 방문 식당 정보 연결
* 캘린더 :  날짜별로 과거 외식 기록을 확인하고 관리
* 재방문 :  다시 방문하고 싶은 식당과 외식 경험 관리
* 동반자 :  누구와 함께한 외식이었는지 함께 기록
* AI 추천 :  누적된 실제 방문 기록과 사용자 취향을 기반으로 식당 추천
* OAuth2 :  Kakao·Naver 계정을 이용한 간편 로그인

<br>

---

## 📄 Documents

* #### 운영

  * Web :  PIKONE Web
  * Backend :  Spring Boot API Server
  * Frontend :  React Web Client

<br>

* #### [BE] Backend

  * OAuth2 · JWT 기반 인증/인가
  * 외식 기록 및 캘린더 API
  * 동반자 관리
  * 이미지 업로드 및 처리
  * EXIF 기반 사진 메타데이터 분석
  * OpenAI 기반 이미지 분석
  * Kakao 장소 검색 연동
  * 사용자 방문 기록 기반 식당 추천

<br>

* #### [FE] Frontend

  * React + TypeScript 기반 SPA
  * TanStack Query 기반 Server State 관리
  * 외식 기록 작성/조회/수정
  * 캘린더 기반 기록 탐색
  * 동반자 관리
  * AI 식당 추천
  * OAuth2 로그인 및 세션 처리
  * Mobile First UI/UX

<br>

---

## 📹 Demo

> 아래 이미지 URL은 PIKONE 스크린샷을 GitHub에 업로드한 뒤 교체합니다.

### Main Page

|                     **홈**                    |                    **외식 기록**                   |                  **AI 추천**                 |
| :------------------------------------------: | :--------------------------------------------: | :----------------------------------------: |
| <img src="HOME_SCREENSHOT_URL" width="100%"> | <img src="RECORD_SCREENSHOT_URL" width="100%"> | <img src="AI_SCREENSHOT_URL" width="100%"> |

<br>

### Record & Calendar

|                      **캘린더**                     |                       **기록 상세**                       |                      **기록 작성**                     |
| :----------------------------------------------: | :---------------------------------------------------: | :------------------------------------------------: |
| <img src="CALENDAR_SCREENSHOT_URL" width="100%"> | <img src="RECORD_DETAIL_SCREENSHOT_URL" width="100%"> | <img src="RECORD_ADD_SCREENSHOT_URL" width="100%"> |

<br>

### Companion & My Page

|                      **동반자**                      |                    **마이페이지**                   |                   **외식 피드**                  |
| :-----------------------------------------------: | :--------------------------------------------: | :------------------------------------------: |
| <img src="COMPANION_SCREENSHOT_URL" width="100%"> | <img src="MYPAGE_SCREENSHOT_URL" width="100%"> | <img src="FEED_SCREENSHOT_URL" width="100%"> |

<br>

---

## 💡 Tech Stack

|                                                                                                                                                                                                                    Frontend                                                                                                                                                                                                                    |                                                                                                                                                                                                  Backend                                                                                                                                                                                                  |                                                                                                                                                     Security                                                                                                                                                     |                                               Database                                              |                                                                                                                                                                                                                      Infra / Other                                                                                                                                                                                                                      |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=React&logoColor=white"/><br><img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=TypeScript&logoColor=white"/><br><img src="https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=Vite&logoColor=white"/><br><img src="https://img.shields.io/badge/TanStack_Query-FF4154?style=flat-square&logo=reactquery&logoColor=white"/> | <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=SpringBoot&logoColor=white"/><br><img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white"/><br><img src="https://img.shields.io/badge/JPA-59666C?style=flat-square"/><br><img src="https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white"/> | <img src="https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=SpringSecurity&logoColor=white"/><br><img src="https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white"/><br><img src="https://img.shields.io/badge/OAuth2-4285F4?style=flat-square"/> | <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=MySQL&logoColor=white"/> | <img src="https://img.shields.io/badge/Amazon_AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white"/><br><img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white"/><br><img src="https://img.shields.io/badge/Kakao_API-FFCD00?style=flat-square&logo=kakao&logoColor=000000"/><br><img src="https://img.shields.io/badge/Naver-03C75A?style=flat-square&logo=naver&logoColor=white"/> |

```text
- Frontend : React, TypeScript, Vite, TanStack Query, Emotion
- Backend : Spring Boot, Java, Spring Data JPA, OpenAI
- Security : Spring Security, OAuth2, JWT
- Database : MySQL
- External API : Kakao, Naver, OpenAI
- Infrastructure : AWS EC2, AWS RDS, Github Actions
```

<br>

---

## 🗂️ Database

<details open>
  <summary>&nbsp;<strong>MySQL</strong>&nbsp;:&nbsp;&nbsp;<strong>서비스 데이터</strong>&nbsp;&nbsp;⇒&nbsp;&nbsp;사용자, 식당, 외식 기록, 동반자 등</summary>

<br>

<!-- ERD 이미지 업로드 후 교체 -->

<img width="1470" alt="PIKONE MySQL ERD" src="PIKONE_ERD_IMAGE_URL">

<br>

PIKONE의 핵심 데이터는 사용자의 **외식 경험**을 중심으로 구성됩니다.

| Domain         | Description                |
| -------------- | -------------------------- |
| User           | 사용자 및 OAuth 계정 정보          |
| DiningRecord   | 사용자의 외식 기록                 |
| Restaurant     | 방문한 식당 정보                  |
| Companion      | 함께 식사한 동반자                 |
| DraftRecord    | 사진 분석 후 사용자가 확정하기 전의 임시 기록 |
| HomeLocation   | 추천 등에 활용하는 사용자 기준 위치       |
| AuthSession    | Refresh Token 기반 로그인 세션    |
| Recommendation | 사용자 기록 기반 식당 추천            |

</details>

<br>

---

## 💻 Architecture

### System

<!-- draw.io 등으로 아키텍처 작성 후 이미지 URL 교체 -->

<img width="1470" alt="PIKONE System Architecture" src="PIKONE_ARCHITECTURE_IMAGE_URL">

```text
React / TypeScript
        ↓
      HTTPS
        ↓
Spring Boot REST API
        ↓
 ┌──────────────┬──────────────┬──────────────┐
 ↓              ↓              ↓              ↓
MySQL        OpenAI         Kakao API      OAuth2
AWS RDS                     Local API    Kakao/Naver
```

```text
- Frontend : React + TypeScript + Vite
- Backend : Spring Boot + Java
- Database : AWS RDS MySQL
- Backend Deployment : AWS EC2
- Authentication : Spring Security + OAuth2 + JWT
- AI : OpenAI API
- Location : Kakao Local API
- CI/CD : Github Actions
```

<br>

### Record Pipeline

PIKONE은 사용자가 모든 정보를 직접 입력해야 하는 기록 방식을 줄이기 위해
사진을 중심으로 기록 생성 과정을 구성합니다.

```text
음식 사진
   ↓
이미지 업로드
   ↓
EXIF / Metadata 분석
   ↓
이미지 전처리
   ↓
OpenAI Vision 분석
   ↓
위치 / 식당 후보 탐색
   ↓
Kakao Local API
   ↓
Draft Record 생성
   ↓
사용자 확인 및 수정
   ↓
Dining Record 저장
```

자동 분석 결과를 곧바로 사용자의 최종 기록으로 저장하지 않고,
**Draft → 사용자 확인 → 최종 기록** 단계를 거쳐 분석 결과와 사용자 확정 데이터를 분리합니다.

<br>

### Recommendation

사용자의 실제 외식 기록을 기반으로 다음 식당을 추천합니다.

```text
Dining Records
      ↓
방문 기록 / 재방문 / 취향 분석
      ↓
추천 조건 생성
      ↓
Restaurant Candidate
      ↓
후보 필터링
      ↓
OpenAI
      ↓
추천 결과 생성
      ↓
사용자에게 추천
```

LLM 호출 자체가 추천 시스템 전체가 되지 않도록
사용자 기록 조회, 후보 식당 선정, 조건 검증과 결과 조립을 Backend의 각 책임으로 분리합니다.

<br>

---

## 📂 Directory Structure

<details open>
  <summary>&nbsp;<strong>Backend</strong>&nbsp;:&nbsp;&nbsp;Open!</summary>

<br>

```text
--------------------------------------------------------------------------------
[ Backend ]
--------------------------------------------------------------------------------

src/main/java
│
├── config
│   └── Security / Application Configuration
│
├── feature
│   ├── authentication
│   │   ├── controller
│   │   ├── application
│   │   ├── domain
│   │   └── infrastructure
│   │
│   └── ...
│
├── controller
│
├── service
│
├── repository
│
├── domain
│
├── dto
│
├── security
│
├── recommendation
│
└── util

src/test/java
│
├── unit
├── integration
└── contract
```

</details>

<br>

<details>
  <summary>&nbsp;<strong>Frontend Web</strong>&nbsp;:&nbsp;&nbsp;Open!</summary>

<br>

```text
--------------------------------------------------------------------------------
[ Frontend ]
--------------------------------------------------------------------------------

src
│
├── api
│
├── components
│   ├── common
│   └── ...
│
├── features
│   ├── auth
│   ├── record
│   ├── calendar
│   ├── companion
│   └── recommendation
│
├── pages
│
├── layouts
│
├── hooks
│
├── styles
│
├── types
│
└── utils
```

</details>

<br>

---

## 👨‍💻 Developer

|     [박정우](https://github.com/jwoo13)    |
| :-------------------------------------: |
|     **Backend & Frontend Developer**    |
| Spring Boot · Java · React · TypeScript |

<br>
