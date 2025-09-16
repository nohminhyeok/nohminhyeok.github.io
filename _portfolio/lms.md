---
title: "학원용 LMS 시스템"
collection: portfolio
permalink: /portfolio/lms/
excerpt: "세미 팀 프로젝트"
thumb: /images/semi.png
---

<section class="proj-meta card">
  <p><strong>기간</strong>: 2025.06.09 ~ 2025.06.25<br>
  <strong>역할</strong>: 관리자 관련 페이지 구현</p>
  <p><strong>주요 구현</strong><br>
  강의관리 · 학생 관리 · 관리자 화면/데이터 연동 · 출석 통계/현황표</p>
  <p><strong>GitHub</strong>:
    <a href="https://github.com/semi-lms/lms.git" target="_blank" rel="noopener">LMS</a>
  </p>
    <p><strong>사이트</strong>:
    <a href="http://3.37.37.185:8082/" target="_blank" rel="noopener">실행 주소</a>
  </p>
</section>

## 프로젝트 개요
<div class="card">
  <p><strong>목표</strong>: 학원 운영자가 강의/학생/출석을 한 곳에서 관리하고, 출석 통계를 빠르게 확인할 수 있는 관리자 화면 제공</p>
  <p><strong>성과</strong>: 관리자 화면 공통화(검색/정렬/페이징), 출석 통계 집계/시각화</p>
</div>

## 담당 역할 & 기여도
<div class="card">
- 관리자 기능 구현: 강의/학생 CRUD, 출석 현황표, 통계 화면 <br>
- 데이터 연동: 출석 집계 쿼리(기간/강의/학생 필터), 페이징·검색(DataTables)  <br>
- 문서화: 요구사항 정리, 테이블 정의서 초안, 회의록/이슈 정리
</div>


## 데이터 모델(ERD)
<div class="card">
  <img src="/assets/docs/lms/4.ERD_B조(LMS).png" alt="LMS ERD" loading="lazy">
</div>

## 핵심 기능
<div class="card">
- 강의 관리: 개설/수정/폐강, 강사 배정, 수강생 매핑  
- 학생 관리: 등록/정보수정, 강의 배정, 상태 관리  
- 출석 관리: 일자별 출석 입력/일괄 처리, 기간 통계(지각/결석 비율)  
- 공통 UI: 검색/정렬/페이징(DataTables), 엑셀 다운로드
</div>

## 문제 해결 사례
<div class="card">
<p><strong>① 월별 출석표에 공휴일 반영하기</strong><br>
접근: DB에 holidays 테이블 생성 후 1년치 공휴일 입력<br>
결과: 공휴일 반영은 됐으나 공휴일 API가 있다는 것을 몰랐고,
 추후 다른 프로젝트에서 반영하였음</p>

<p><strong>② 강사 선택 시 오류</strong><br>
접근: 강의를 진행하고 있는 강사는 선택이 되지 않아야 하는데 선택되는 오류 발생<br>
결과: 화면/인쇄 모두 정상 표시</p>
</div>

## 산출물
<div class="card doc-list">
  <ul>
    <li><a href="/assets/docs/lms/1.WBS_B조(LMS).xlsx">WBS</a></li>
    <li><a href="/assets/docs/lms/2.요구사항정의서_B조(LMS).xlsx">요구사항정의서</a></li>
    <li><a href="/assets/docs/lms/3.테이블정의서_B조(LMS).xlsx">테이블정의서</a></li>
    <li><a href="/assets/docs/lms/4.ERD_B조(LMS).png" target="_blank">ERD</a></li>
    <li><a href="/assets/docs/lms/5.화면설계서_B조(LMS).pptx">화면설계서</a></li>
  </ul>
</div>

## 시연 영상
<div class="video card">
  <iframe src="https://www.youtube.com/embed/pMJFGojjcC4"
    title="LMS 프로젝트 시연영상"
    frameborder="0" allowfullscreen></iframe>
</div>
