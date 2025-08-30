# 🛍️ AIMAE: 고민 많은 당신을 위한 AI 쇼핑 메이트

> 멀티모달 입력(텍스트 + 이미지)을 활용한 개인 맞춤형 제품 추천 및 비교 서비스

---

## 📌 프로젝트 소개

**AIMAE**는 사용자의 텍스트 질문이나 제품 사진을 바탕으로, 상황에 맞는 제품을 추천하고 비교 분석해주는 AI 쇼핑 어시스턴트입니다.

> "복잡한 쇼핑 고민, 한 줄 질문이나 사진 한 장으로 해결하세요!"

---

## 3. 프로젝트 기간

2025년 7월 28일 \~ 2025년 8월 28일 (1개월)

---

## 4. 주요 기능

* **멀티모달 입력 기반 제품 추천**

  * 텍스트, 이미지, 혹은 동시 입력 가능
* **한눈에 보는 제품 정보**

  * 가격, 상세 내용, 리뷰 비교표 제공
* **간편한 구매**

  * 장바구니 기능: 추가, 삭제, 수량 변경
  * 클릭 시 바로 결제 연동
* **SNS 로그인 및 결제 연동**

  * 카카오/네이버 로그인
  * 아임포트 결제 API

---

## 5. 기술 스택

| 구분     | 기술                            |
| ------ | ----------------------------- |
| 언어     | [![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge\&logo=python\&logoColor=white)]() [![Java](https://img.shields.io/badge/Java-007396?style=for-the-badge\&logo=java\&logoColor=white)]()                  |
| 프론트엔드  | [![HTML](https://img.shields.io/badge/HTML-E34F26?style=for-the-badge\&logo=html5\&logoColor=white)]() [![CSS](https://img.shields.io/badge/CSS-1572B6?style=for-the-badge\&logo=css3\&logoColor=white)]() [![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)]()         |
| 백엔드    | JSP/Servlet, MyBatis, Flask   |
| 서버     | [![Tomcat](https://img.shields.io/badge/Apache%20Tomcat-F8DC75?style=for-the-badge\&logo=apachetomcat\&logoColor=white)]()                |
| 데이터베이스 | [![Oracle](https://img.shields.io/badge/Oracle-F80000?style=for-the-badge\&logo=oracle\&logoColor=white)]()                        |
| AI     | Google ViT, GPT-4o            |
| 라이브러리  | bcrypt                        |
| API    | Kakao 로그인, Naver 로그인, 아임포트 결제 |
| 개발도구   | Eclipse, VSCode               |
| 협업     | [![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge\&logo=github\&logoColor=white)](https://github.com/2025-SMHRD-IS-CLOUD-3/mongglemonggle) [![Figma](https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge\&logo=figma\&logoColor=white)]()             |

---

## 6. 시스템 아키텍처

```
[사용자 입력] --> [웹 UI / React] --> [백엔드: JSP/Servlet, Flask]
           --> [AI 분석: Google ViT, GPT-4o]
           --> [DB: Oracle]
           --> [결과 반환 / 장바구니 / 결제 API 연동]
```

---

## 7. 유스케이스

1. 사용자가 텍스트 또는 이미지 입력
2. AI가 입력 데이터를 분석
3. 조건 기반 맞춤 제품 추천
4. 추천 제품 비교 및 요약
5. 장바구니 담기 및 결제 진행

---

## 8. 서비스 흐름도

```
사용자
  │
  ▼
텍스트/이미지 입력
  │
  ▼
AI 분석 (NLP + 이미지 인식)
  │
  ▼
추천 제품 리스트 + 비교표
  │
  ▼
장바구니 담기 / 결제 진행
  │
  ▼
주문 완료 / 마이페이지 업데이트
```

---

## 9. ER 다이어그램

```
USERS -< ORDERS >- PRODUCTS
USERS -< CART >- PRODUCTS
PRODUCTS -< REVIEWS
```

---

## 10. 화면 구성

* **메인 페이지**: 검색 및 이미지 업로드
* **추천 결과 페이지**: 제품 리스트 + 비교표
* **상세 페이지**: 제품 상세 정보 + 구매 버튼
* **마이페이지**: 회원 정보, 주문 내역, 장바구니 관리

---

## 11. 팀원 역할

| 이름       | 역할 및 담당                                                         |
| -------- | --------------------------------------------------------------- |
| 한찬희 (팀장) | 총괄, PM, 기획/DB/설계/문서, UI/UX, 프론트엔드·백엔드 개발, PPT/발표                |
| 임진서      | 기획/설계/문서, 백엔드, AI 모델 파인튜닝, API 연동(OpenAI, Iamport), 데이터 수집, PPT |
| 오정관      | DB 설계/구축, 백엔드, 장바구니 기능 구현, 자료 수집                                |
| 양용석      | 백엔드, 회원 기능 구현(가입, 정보 변경, 삭제/수정), 자료 수집                          |

---

## 12. 트러블슈팅

* **AI 모델 성능 문제**: 입력 이미지와 텍스트 불일치 → 데이터셋 재수집 및 모델 재학습
* **결제 연동 오류**: 아임포트 API 테스트 모드에서 CORS 오류 → 서버측 프록시 설정으로 해결
* **브라우저 호환성 문제**: 일부 CSS 반응형 깨짐 → 미디어 쿼리 추가 및 테스트
* **DB 외래키 제약조건 문제**: 회원 삭제 시 CART 테이블 레코드 미삭제 → `ON DELETE CASCADE` 적용

```
```




