---
permalink: /
title: ""
layout: single
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

# 안녕하세요, 노민혁입니다
**백엔드 개발자 지망생**으로서 안정적인 트랜잭션, 명확한 데이터 모델링, 그리고 “끝까지 파는” 문제 해결을 지향합니다.  
아래에서 제가 잘하는 것과 실제로 해결한 사례를 빠르게 보실 수 있습니다.

<div class="btns">
  <a class="btn btn--primary" href="/portfolio/">포트폴리오 보기</a>
  <a class="btn" href="/cv/">이력서 보기</a>
  <a class="btn" href="https://github.com/freestyle-y" target="_blank" rel="noopener">GitHub</a>
  <a class="btn" href="https://www.notion.so/Dev-Docs-2534f8a9065c8043b6baf42fd9f45e69" target="_blank" rel="noopener">Notion</a>
</div>

---

## 무엇을 잘하나요
- **결제·주문 흐름 설계**: 카카오페이 연동, 주문/결제/적립금/배송지 저장 트랜잭션 정리
- **데이터 모델링 & SQL**: MySQL ERD 설계, 다중 JOIN, Grouping, 성능을 해치지 않는 집계 쿼리
- **문서화/운영 관점**: 에러 원인 추적(로그/SQL), 재발 방지 체크리스트화
- **프런트 협업 포인트**: JSP·DataTables·간단한 React, 관리자 화면 구성과 UX 다듬기

---

## 문제 해결 로그 (요약 사례)
> 실제 프로젝트에서 **무엇을**, **왜**, **어떻게** 고쳤는지 중심으로 정리했습니다.

### 1) 카카오페이 결제 준비→승인 흐름 안정화
- **문제**: 주문정보 저장, 포인트 차감, 결제창 리다이렉트 사이의 순서/예외 처리 혼선  
- **접근**: 컨트롤러→서비스 역할 분리, 주문/결제 레코드 선저장 → 카카오 `ready` 호출 → 승인 시 상태 업데이트  
- **결과**: 실패 시 롤백 지점 명확화, 중복 결제/잘못된 금액 승인 방지

### 2) 전자서명(Data URL) 저장 & 계약서 PDF 반영
- **문제**: 서명 캔버스 이미지가 상세/다운로드본에서 서로 다르게 보임  
- **접근**: Base64 디코드→파일 저장→`Attachment` 엔티티로 메타 관리, 우선순위별(공급자/수요자) 표시 통일  
- **결과**: 화면·PDF 동일 렌더링, 파일 경로/접근 권한 일원화

### 3) DataTables 멀티 헤더/정렬·검색 UX
- **문제**: 헤더 그룹과 정렬 기준 불일치, 드롭다운이 인쇄 레이어에 가려짐  
- **접근**: 고정 폭/열 그룹 CSS 재정의, z-index/print 전용 스타일 분리  
- **결과**: 관리자 목록 가독성↑, 인쇄/화면 UI 충돌 제거

---

## 기술 스택
- **Backend**: Java, Spring Boot, MyBatis, JPA  
- **DB**: MySQL, Oracle  
- **Frontend**: JavaScript, JSP, React(기초)  
- **Infra/Tools**: AWS, GitHub Actions, Docker, Eclipse, IntelliJ

