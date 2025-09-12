---
permalink: /
title: ""
layout: single
author_profile: true
redirect_from:
  - /about/
  - /about.html
classes: wide
---

<div class="home-wrap">

<section class="hero">
  <h2>안녕하세요, 노민혁입니다</h2>
  <p><strong>백엔드 개발자 지망생</strong>으로서 안정적인 트랜잭션, 명확한 데이터 모델링, 그리고 “끝까지 파는” 문제 해결을 지향합니다.<br>
  아래에서 제가 잘하는 것과 실제로 해결한 사례를 빠르게 보실 수 있습니다.</p>

  <div class="btns">
    <a class="btn btn--primary" href="/portfolio/">포트폴리오 보기</a>
    <a class="btn" href="/cv/">이력서 보기</a>
    <a class="btn" href="https://github.com/freestyle-y" target="_blank" rel="noopener">GitHub</a>
    <a class="btn" href="https://www.notion.so/Dev-Docs-2534f8a9065c8043b6baf42fd9f45e69" target="_blank" rel="noopener">Notion</a>
  </div>
</section>

<br>

<section>
  <h2>문제 해결 로그 (요약 사례)</h2>

  <article class="card">
    <h3>1) 카카오페이 포인트가 실제 결제 금액에 미반영</h3>
    <ul class="bullets">
      <li><strong>문제</strong>: 카카오페이 결제 시 포인트 사용분이 실제 승인 금액에 반영되지 않음</li>
      <li><strong>접근</strong>: 적립금 사용 이력 테이블에 <code>kakaoPay_used</code> 컬럼 추가 → 
        <code>ready</code> 요청 금액 = 총액 − 적립금 − 포인트로 계산, 
        <code>approve</code> 응답에서 결제 금액 검증 및 적립금, 포인트 적용 확인</li>
      <li><strong>결과</strong>: 승인 금액 불일치 없이 정상적으로 출력 확인</li>
    </ul>
  </article>

  <article class="card">
    <h3>2) 월별 출결 현황에 공휴일 반영하기</h3> 
    <ul class="bullets"> 
      <li><strong>문제</strong>: 월별 출석표를 제작하는 과정에서 공휴일을 반영해야 함</li> 
      <li><strong>접근</strong>: 1년 단위(2025년) 공휴일을 DB에 입력하여 공휴일 표시</li> 
      <li><strong>결과</strong>: 공휴일 API가 있다는 걸 몰랐고, 이 경험으로 인해 다른 프로젝트에서 활용할 수 있었음</li> 
    </ul> 
  </article>

  <article class="card">
    <h3>3) 회원 적립금 계산식의 NULL 처리 오류</h3>
    <ul class="bullets">
      <li><strong>문제</strong>: 보유 − 사용 계산 시 NULL로 인한 합계 오류</li>
      <li><strong>접근</strong>: MySQL <code>IFNULL</code>로 NULL → 0 치환, 
        합계에는 <code>IFNULL(SUM(...), 0)</code> 패턴 적용</li>
      <li><strong>결과</strong>: 예외 없이 일관된 적립금 표시</li>
    </ul>
  </article>

  <article class="card">
    <h3>4) 적립금과 주문 테이블 조인 시 결과물 중복 제거</h3>
    <ul class="bullets">
      <li><strong>문제</strong>: 주문 테이블과 적립금 사용 내역을 JOIN 시 결과가 여러개로 나옴</li>
      <li><strong>접근</strong>: 주문 테이블에 한 주문에 여러개의 행이 존재하여 JOIN시 여러개가 나오는 것을 확인,<br>
      							적립금 사용 내역에 DISTINCT 식 추가하여 중복된 값 제거</li>
      <li><strong>결과</strong>: 예외 없이 일관된 적립금 표시</li>
    </ul>
  </article>

  <article class="card"> 
  	<h3>5) MyBatis 활용 DB 데이터 입력 오류</h3> 
  	<ul class="bullets"> 
  	  <li><strong>문제</strong>: DB에 데이터 입력 시, 외래키 설정으로 인한 오류 발생</li> 
  	  <li><strong>접근</strong>: 외래키 미설정 후 테스트 진행, 단위테스트 기간에 외래기 설정</li> 
  	  <li><strong>결과</strong>: 외래키 오류 발생 횟수가 줄어들게 되어 오류 해결 기간이 축소</li> 
  	</ul> 
  </article>
</section>


<section>
  <h2>대표 프로젝트</h2>
  <div class="proj-grid">
    <article class="card proj-card">
      <h3>학원용 LMS 시스템</h3>
      <p class="sub">Spring Boot · MyBatis · MySQL</p>
      <ul class="bullets">
        <li>수강생·강의·출결·과제 관리, 권한별 대시보드</li>
        <li>공지/게시판 모듈, 파일 업로드/다운로드</li>
        <li>ERD/트랜잭션 설계 및 테스트 데이터 구축</li>
      </ul>
      <div class="actions">
        <a class="btn btn--primary" href="/portfolio/lms/">자세히 보기</a>
      </div>
    </article>

    <article class="card proj-card">
      <h3>B2B 무역 구매·배송 서비스</h3>
      <p class="sub">결제·주문 · 전자계약 · 물류</p>
      <ul class="bullets">
        <li>카카오페이 연동, 주문/결제/적립금/배송지 트랜잭션</li>
        <li>전자서명 저장(Attachment) → 계약서 PDF 반영</li>
        <li>관리자 DataTables 멀티헤더·정렬/검색 UX</li>
      </ul>
      <div class="actions">
        <a class="btn btn--primary" href="/portfolio/b2b/">자세히 보기</a>
      </div>
    </article>
  </div>
</section>


<section>
  <h2>자격·교육</h2>
  <ul class="badge-grid">
    <li class="badge card">
      <div class="b-title">SQLD</div>
      <div class="b-sub">한국데이터산업진흥원 · 2025.06</div>
    </li>
    <li class="badge card">
      <div class="b-title">구디아카데미 9기</div>
      <a href="/assets/kakaotalk.jpg">수료증</a>
      <div class="b-sub">AWS·Java·Spring Boot · 2025.03~09</div>
    </li>
  </ul>
</section>

<section class="card cta">
  <h2>함께 일할 준비가 되어 있습니다</h2>
  <p>안정적인 트랜잭션과 깔끔한 SQL/모델링을 강점으로 합니다. 필요 시 바로 코드/ERD/로그를 근거로 설명드리겠습니다.</p>
  <div class="btns">
    <a class="btn btn--primary" href="/cv/">이력서 보기</a>
    <a class="btn" href="mailto:kygh1488@naver.com" rel="noopener">메일 보내기</a>
    <a class="btn" href="https://github.com/freestyle-y" target="_blank" rel="noopener">GitHub</a>
  </div>
</section>

</div><!-- /.home-wrap -->
<section>
  <h2>기술 스택</h2>
  <ul class="stack">
    <li>Java</li><li>Spring Boot</li><li>MyBatis</li><li>JPA</li>
    <li>MySQL</li><li>Oracle</li>
    <li>JavaScript</li><li>JSP</li><li>React(기초)</li>
    <li>AWS</li><li>GitHub Actions</li><li>Docker</li>
    <li>Eclipse</li><li>IntelliJ</li>
  </ul>
</section>

<style>
/* ===== Home local styles (라이트/다크 상위 팔레트 상속) ===== */
.home-wrap{ color: inherit; }
.home-wrap h2{
  font-size: clamp(1.25rem, 1.05rem + .9vw, 1.8rem);
  letter-spacing: -0.01em; line-height: 1.3; margin: .6rem 0 .8rem;
}
.home-wrap h3{ font-size: 1.05rem; margin: .7rem 0 .4rem; }
.hero{ margin-top: .2rem; margin-bottom: .6rem; }
.btns{ display:flex; flex-wrap:wrap; gap:10px; margin: 12px 0 4px; }

/* 카드 공통 */
.card{
  background: inherit; /* 페이지 배경과 동일 */
  border: 1px solid;
  border-color: rgba(128,128,128,.25); /* fallback */
  border-color: color-mix(in oklch, currentColor 18%, transparent);
  border-radius: 14px;
  padding: 12px 14px;
  margin: 10px 0 12px;
  box-shadow: none;
}

/* 리스트/불릿/스택 */
.list{ margin: 0; padding-left: 18px; }
.bullets{ margin: 4px 0 2px; padding-left: 18px; }
.stack{
  list-style: none; margin: 0; padding: 0;
  display: flex; flex-wrap: wrap; gap: 8px;
}
.stack li{
  border: 1px solid color-mix(in oklch, currentColor 30%, transparent);
  background: color-mix(in oklch, currentColor 8%, transparent);
  padding: 4px 10px; border-radius: 999px; font-weight: 600;
}

/* === 메인 강화 컴포넌트 === */

/* 프로젝트 카드 그리드 */
.proj-grid{
  display: grid;
  grid-template-columns: repeat(2, minmax(260px,1fr));
  gap: 14px;
  margin: 8px 0 4px;
}
@media (max-width: 900px){
  .proj-grid{ grid-template-columns: 1fr; }
}
.proj-card .sub{
  opacity: .8;
  margin-top: -2px;
  margin-bottom: 6px;
  font-size: .95rem;
}
.actions{ display:flex; gap:8px; margin-top: 4px; }

/* 숫자 카드 */
.nums{
  display:grid;
  grid-template-columns: repeat(3, minmax(140px,1fr));
  gap: 12px;
}
@media (max-width: 720px){
  .nums{ grid-template-columns: 1fr; }
}
.num{
  border:1px solid color-mix(in oklch, currentColor 18%, transparent);
  border-radius: 14px;
  padding: 14px 16px;
  text-align:center;
  background: color-mix(in oklch, currentColor 6%, transparent);
}
.num strong{
  display:block;
  font-size: clamp(1.2rem, 1rem + 1vw, 1.8rem);
  letter-spacing: -0.01em;
}
.num span{
  display:block; margin-top:2px; opacity:.75;
}

/* 배지(자격/교육) */
.badge-grid{
  list-style:none; margin:0; padding:0;
  display:grid; gap:10px;
  grid-template-columns: repeat(2, minmax(220px,1fr));
}
@media (max-width: 720px){
  .badge-grid{ grid-template-columns: 1fr; }
}
.badge{ padding: 10px 12px; }
.badge .b-title{ font-weight:700; }
.badge .b-sub{ opacity:.8; font-size:.95rem; }

/* CTA 카드 */
.cta{ margin-top: 16px; }
.cta p{ margin: 6px 0 10px; opacity:.95; }

/* 반응형 보정 */
@media (max-width: 720px){
  .btns{ gap:8px; }
}
</style>

<!-- (선택) SEO 보강 JSON-LD -->
<script type="application/ld+json">
{
  "@context":"https://schema.org",
  "@type":"Person",
  "name":"노민혁",
  "jobTitle":"Backend Developer (Junior)",
  "email":"mailto:kygh1488@naver.com",
  "sameAs":["https://github.com/freestyle-y"]
}
</script>
