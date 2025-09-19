---
title: "B2B 무역 구매·배송 서비스"
collection: portfolio
permalink: /portfolio/b2b/
excerpt: "파이널 팀 프로젝트"
thumb: /images/final.png
---

<section class="proj-meta card">
  <p><strong>기간</strong>: 2025.07.25 ~ 2025.09.09<br>
  <strong>역할</strong>: 주문·결제 / 견적서 / 계약 모듈</p>
  <p><strong>주요 구현</strong><br>
  결제(카카오페이 API, 주소 API), 주문 조회 상세, 견적서, 계약(전자서명·PDF), 공휴일 API 일정/대금 입력</p>
  <p><strong>GitHub</strong>:
    <a href="https://github.com/freestyle-y/final_project_b2b" target="_blank" rel="noopener">B2B</a>
  </p>
  <p><strong>사이트</strong>:
    <a href="http://3.37.37.185/" target="_blank" rel="noopener">실행 주소</a>
  </p>
  
  <p>
  	<strong>수정중</strong><br>
  	1. 메인페이지 페이징 제거, 상품 추가(완료)<br>
  	2. 네이버, 카카오 로그인 properties 수정(완료)
  </p>
</section>

## 프로젝트 개요
<div class="card">
  <p><strong>목표</strong>: 기업회원 상품 주문 → 견적서 작성/승인 → 계약서 작성/서명 → 계약금 입금 확인 → 컨테이너 상품 입력 → 배송 → 잔금 미 입금 시 상품 회수 → 회수 된 상품은 B2C로 전환</p>
  <p><strong>성과</strong>: 기업 회원의 주문부터 상품 회수까지의 단계가 문제 없이 진행</p>
  <p><strong>팀/기간</strong>: 4인, 2025.07.25 ~ 2025.09.09</p>
</div>

## 담당 역할 & 기여도
<div class="card">
- 결제/주문: 카카오페이 Ready/Approve, 주문/포인트/배송지 저장 <br>
- 견적/계약: 전자서명 DataURL 저장→PDF 반영, 계약상태/대금 스케줄 관리 <br>
- 조회/관리: 주문 상세, 배송조회, 관리자 기업회원 견적서 계약서 <br>
- 문서화: 테이블 정의·요구사항·회의록, 화면설계서 반영
</div>

## 데이터 모델(ERD)
<div class="card">
  <img src="/assets/docs/b2b/4. ERD_Y조(B2B 무역).png" alt="B2B ERD" loading="lazy">
</div>

## 핵심 기능
<div class="card">
- 주문/결제: 장바구니·주문 생성, 포인트 사용/적립, 상품 결제 <br>
- 견적/계약: 견적서 작성·승인, 계약 전자서명, 계약 PDF 다운로드 <br>
- 배송: 컨테이너 등록·상태, 배송현황 표시, 회수/완료 처리  <br>
- 통합 UI: 페이징/정렬/검색, 멀티 헤더 테이블
</div>

## 문제 해결 사례
<div class="card">
<p><strong>① 카카오페이 정합성</strong><br>
접근: 주문/결제/포인트 선저장 → Ready 응답 저장 → 승인 시 상태 전이<br>
결과: 중복 승인/실패 방지</p>

<p><strong>② FK 제약으로 수정 삭제 오류 발생</strong><br>
접근: 초기 외래키 설정하지 않고 데이터 DML 진행<br>
결과: 오류 발생 횟수가 크게 줄어들어 프로젝트 진행 시 원활하게 진행됨</p>
</div>

## 산출물
<div class="card doc-list">
  <ul>
    <li><a href="/assets/docs/b2b/1. WBS_Y조(B2B무역).xlsx">WBS</a></li>
    <li><a href="/assets/docs/b2b/2. 요구사항 정의서_Y조(B2B 무역).xlsx">요구사항정의서</a></li>
    <li><a href="/assets/docs/b2b/3. 테이블 정의서_Y조(B2B 무역).xlsx">테이블정의서</a></li>
    <li><a href="/assets/docs/b2b/4. ERD_Y조(B2B 무역).png" target="_blank">ERD</a></li>
    <li><a href="/assets/docs/b2b/5. 화면설계서_Y조(B2B 무역).pptx">화면설계서</a></li>
    <li><a href="/assets/docs/b2b/7. 발표 PPT_Y조(B2B 무역).pptx">발표 PPT</a></li>
  </ul>
</div>

## 시연 영상
<div class="video card">
  <iframe src="https://www.youtube.com/embed/USnFH2vjaoQ"
    title="B2B 프로젝트 시연영상"
    frameborder="0" allowfullscreen></iframe>
</div>

