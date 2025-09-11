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
    <h3>1) 카카오페이 결제 준비→승인 흐름 안정화</h3>
    <ul class="bullets">
      <li><strong>문제</strong>: 주문정보 저장, 포인트 차감, 결제창 리다이렉트 사이의 순서/예외 처리 혼선</li>
      <li><strong>접근</strong>: 컨트롤러→서비스 역할 분리, 주문/결제 레코드 선저장 → 카카오 <code>ready</code> 호출 → 승인 시 상태 업데이트</li>
      <li><strong>결과</strong>: 실패 시 롤백 지점 명확화, 중복 결제/잘못된 금액 승인 방지</li>
    </ul>
  </article>

  <article class="card">
    <h3>2) 전자서명(Data URL) 저장 &amp; 계약서 PDF 반영</h3>
    <ul class="bullets">
      <li><strong>문제</strong>: 서명 캔버스 이미지가 상세/다운로드본에서 서로 다르게 보임</li>
      <li><strong>접근</strong>: Base64 디코드→파일 저장→<code>Attachment</code> 엔티티 메타 관리, 우선순위별(공급자/수요자) 표시 통일</li>
      <li><strong>결과</strong>: 화면·PDF 동일 렌더링, 파일 경로/접근 권한 일원화</li>
    </ul>
  </article>

  <article class="card">
    <h3>3) DataTables 멀티 헤더/정렬·검색 UX</h3>
    <ul class="bullets">
      <li><strong>문제</strong>: 헤더 그룹과 정렬 기준 불일치, 드롭다운이 인쇄 레이어에 가려짐</li>
      <li><strong>접근</strong>: 고정 폭/열 그룹 CSS 재정의, z-index/print 전용 스타일 분리</li>
      <li><strong>결과</strong>: 관리자 목록 가독성 향상, 인쇄/화면 UI 충돌 제거</li>
    </ul>
  </article>
</section>

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

</div><!-- /.home-wrap -->

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

@media (max-width: 720px){
  .btns{ gap:8px; }
}
</style>
