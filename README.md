# Git Practice
메인에서 수정했습니다.
branch 수정
또수정
# 🚀 Project Name: Coffee-Order-System

> **Java/Spring Boot 기반의 고성능 주문 관리 백엔드 API 서비스** > 실무에서 경험한 주문 로직을 추상화하여 확장성과 성능을 고려해 재구현한 프로젝트입니다.

---

## 🛠 Tech Stack
- **Language:** Java 17
- **Framework:** Spring Boot 3.x
- **Database:** MySQL 8.0, Redis (Cache)
- **ORM:** Spring Data JPA (Querydsl)
- **Test:** JUnit5, Mockito

---

## ✨ Key Features
- **비즈니스 로직 최적화:** 동시성 이슈를 고려한 재고 관리 시스템 구현 (Redisson 분산 락 활용)
- **RESTful API 설계:** 표준 HTTP 상태 코드 및 일관된 응답 객체 정의
- **성능 개선:** 자주 조회되는 메뉴 정보에 Redis 캐싱 적용하여 DB 부하 20% 감소

---

## 🏗 Architecture & Design Patterns
- **Layered Architecture:** 관심사 분리를 통한 유지보수성 향상
- **Strategy Pattern:** 결제 수단 확장을 고려한 결제 로직 설계
- **SOLID 원칙 준수:** 의존성 주입(DI)을 통한 결합도 감소 및 유연한 구조

---

## 📝 Trouble Shooting
### 1. 동시 주문 시 재고 정합성 문제
- **Problem:** 동시에 100명이 주문할 때 재고가 마이너스가 되는 현상 발생
- **Solution:** 비관적 락(Pessimistic Lock)과 Redis 분산 락을 비교 분석하여, 시스템 환경에 적합한 Redis 방식을 선택해 해결