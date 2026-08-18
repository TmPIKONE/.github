# PIKONE 🍽️

> **사진으로 남기는 나만의 외식 기록, 그리고 기록을 기반으로 한 다음 식당 추천**

PIKONE은 매번 다녀온 식당을 따로 기억하거나 정리해야 하는 불편함에서 시작한 **개인 외식 기록 서비스**입니다.

사진과 함께 방문한 식당을 기록하고, 캘린더를 통해 지난 외식 경험을 다시 확인할 수 있습니다.
쌓인 방문 기록과 취향을 기반으로 사용자에게 어울리는 다음 식당도 추천합니다.

<br>

## ✨ Key Features

* 📸 **외식 기록** — 사진과 함께 방문한 식당과 음식 기록
* 🗓️ **캘린더** — 날짜별 외식 기록 조회 및 관리
* 👥 **동반자 기록** — 누구와 함께했는지 기록
* 🔍 **사진 분석** — EXIF와 이미지 분석을 활용한 기록 작성 보조
* 🤖 **AI Recommendation** — 실제 방문 기록과 취향을 기반으로 식당 추천
* 🔐 **OAuth2 Login** — Kakao / Naver 로그인 지원

<br>

## 🏗 Architecture

```text
                 PIKONE

┌───────────────────────────────┐
│       React / TypeScript      │
│            Frontend           │
└───────────────┬───────────────┘
                │ REST API
                ▼
┌───────────────────────────────┐
│       Spring Boot / Java      │
│            Backend            │
├───────────────────────────────┤
│ OAuth2 · JWT · JPA · AI       │
└───────────────┬───────────────┘
                │
        ┌───────┴────────┐
        ▼                ▼
      MySQL          External APIs
                     Kakao · OpenAI
```

<br>

## 🛠 Tech Stack

### Backend

`Java` `Spring Boot` `Spring Security` `Spring Data JPA` `MySQL`
`OAuth2` `JWT` `Gradle`

### Frontend

`React` `TypeScript` `Vite` `React Query` `Emotion`

### Infrastructure

`AWS EC2` `AWS RDS` `GitHub Actions`

### External

`Kakao API` `Naver OAuth` `OpenAI API`

<br>

## 📂 Repository

| Repository   | Description                            |
| ------------ | -------------------------------------- |
| **Backend**  | Spring Boot 기반 API 서버, 인증·기록·추천·이미지 처리 |
| **Frontend** | React 기반 PIKONE Web Client             |

<br>

## 🔎 What We Focus On

PIKONE은 기능 구현에 그치지 않고 실제 서비스를 운영하고 확장할 수 있는 구조를 고민합니다.

* OAuth2와 JWT 기반의 인증 흐름 설계
* 이미지 분석부터 기록 생성까지의 처리 Pipeline 분리
* 외부 AI에 모든 판단을 위임하지 않는 추천 구조
* 명확한 Transaction Boundary와 Domain 책임 분리
* Frontend / Backend API Contract 보호
* 테스트 가능한 구조와 지속적인 리팩토링

<br>

---

### PIKONE

**Record your taste. Remember your moments. Find your next place.**
