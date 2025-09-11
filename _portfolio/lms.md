---
title: "학원용 LMS 시스템"
collection: portfolio
permalink: /portfolio/lms/   # (수정) 명확한 경로
excerpt: "세미 팀 프로젝트<br/><img src='/images/semi.png'>"
---

<p><strong>기간</strong>: 2025.06.09 ~ 2025.06.25<br>
<strong>역할</strong>: 관리자 관련 페이지 구현</p>

<p><strong>주요 구현</strong><br>
강의관리 · 학생 관리 · 관리자 화면/데이터 연동 · 출석 통계/현황표
</p>

<p><strong>GitHub</strong>: <a href="https://github.com/semi-lms/lms.git" target="_blank" rel="noopener">LMS</a></p>

---

## 프로젝트 개요
<p><strong>목표</strong>: 학원 운영자가 강의/학생/출석을 한 곳에서 관리하고, 출석 통계를 빠르게 확인할 수 있는 관리자 화면 제공</p>
<p><strong>성과</strong>: 관리자 화면 공통화(검색/정렬/페이징), 출석 통계 집계/시각화, 엑셀 기반 산출물 흐름 정리</p>
<p><strong>기간</strong>: 2025.06.09 ~ 2025.06.25</p>

---

## 담당 역할 & 기여도
- 관리자 기능 구현: 강의/학생 CRUD, 출석 현황표, 통계 화면
- 데이터 연동: 출석 집계 쿼리(기간/강의/학생 필터), 페이징·검색(DataTables)
- 운영 편의: 엑셀 내보내기, 화면 설계서 반영(컴포넌트 공통화)
- 문서화: 요구사항 정리, 테이블 정의서 초안, 회의록/이슈 정리

---

## 시스템 구조(요약)
<p>Admin(JSP) ↔ Spring Boot ↔ MyBatis ↔ MySQL</p>

---

## 데이터 모델(ERD)
<p><img src="/assets/docs/lms/4.ERD_B조(LMS).png" alt="LMS ERD" loading="lazy"></p>

---

## 핵심 기능
- <strong>강의 관리</strong>: 개설/수정/폐강, 강사 배정, 수강생 매핑
- <strong>학생 관리</strong>: 등록/정보수정, 강의 배정, 상태 관리
- <strong>출석 관리</strong>: 일자별 출석 입력/일괄 처리, 기간 통계(지각/결석 비율)
- <strong>공통 UI</strong>: 검색/정렬/페이징(DataTables), 엑셀 다운로드

---

## 문제 해결 사례
<p><strong>① 출석 통계 성능 저하</strong><br>
문제: 일자/강의/학생 필터 조합에 따라 조회가 급격히 느려짐<br>
접근: <code>attendance(lecture_id, student_id, att_date)</code> 복합 인덱스 추가, 기간 조건 선필터링 → 통계 서브쿼리 축소<br>
결과: 통계 화면 응답 안정화, 관리자 UX 개선</p>

<p><strong>② DataTables 정렬/인쇄 충돌</strong><br>
문제: 드롭다운이 인쇄 레이어에 가려짐<br>
접근: z-index / <code>@media print</code> 전용 CSS 분리, 헤더 그룹 고정폭 적용<br>
결과: 화면/인쇄 모두 정상 표시</p>

<p><strong>③ 엑셀 내보내기 포맷 통일</strong><br>
문제: 컬럼 순서/날짜 포맷 불일치<br>
접근: 서버단 DTO→Export 변환 계층 분리, 공통 유틸 포맷터<br>
결과: 운영자가 문서 바로 제출 가능</p>

---

## 산출물(다운로드/보기)
<ul class="doc-list">
  <li><a href="/assets/docs/lms/1.WBS_B조(LMS).xlsx">1.WBS_B조(LMS).xlsx</a></li>
  <li><a href="/assets/docs/lms/2.요구사항정의서_B조(LMS).xlsx">2.요구사항정의서_B조(LMS).xlsx</a></li>
  <li><a href="/assets/docs/lms/3.테이블정의서_B조(LMS).xlsx">3.테이블정의서_B조(LMS).xlsx</a></li>
  <li><a href="/assets/docs/lms/4.ERD_B조(LMS).png" target="_blank" rel="noopener">4.ERD_B조(LMS).png</a></li>
  <li>
    <a href="/assets/docs/lms/5.화면설계서_B조(LMS).pptx">5.화면설계서_B조(LMS).pptx</a>
  </li>
</ul>
---


## 시연 영상
<div class="video">
  <iframe
    src="https://www.youtube.com/embed/pMJFGojjcC4"
    title="LMS 프로젝트 시연영상"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen></iframe>
</div>


<style>
.video{position:relative;padding-bottom:56.25%;height:0;overflow:hidden}
.video iframe{position:absolute;top:0;left:0;width:100%;height:100%}
.doc-list{margin:0;padding-left:1.2rem}
.doc-list li{margin:.2rem 0}
.note{font-size:.9rem;color:#666}
</style>
