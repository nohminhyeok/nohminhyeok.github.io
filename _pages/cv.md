---
permalink: /cv/
title: "이력서"
layout: single
author_profile: true
classes: wide
---
<br>
<div class="cv-wrap">

<h2>기본정보</h2>
<div class="cv-card">
  <dl class="kv">
    <div><dt>이름</dt><dd>노민혁 (Noh Min Hyeok)</dd></div>
    <div><dt>출생</dt><dd>1997년생</dd></div>
    <div><dt>지원분야</dt><dd>백엔드 개발 (신입)</dd></div>
    <div><dt>휴대폰</dt><dd>010-9873-1878</dd></div>
    <div><dt>이메일</dt><dd>kygh1488@naver.com</dd></div>
    <div><dt>주소</dt><dd>서울특별시 관악구 신림로 56길 19-10 행복이꽃피는집 203호</dd></div>
  </dl>
</div>

<h2>학력</h2>
<div class="cv-card">
  <ul class="timeline">
    <li>
      <div class="row">
        <strong>대전보건대학교</strong> 의무부사관과 전문학사
        <span class="period">2015.03 ~ 2017.02</span>
      </div>
      <div class="meta">학점: 3.5 / 4.5</div>
    </li>
    <li>
      <div class="row">
        <strong>고창고등학교</strong> 졸업
        <span class="period">2012.03 ~ 2015.02</span>
      </div>
    </li>
  </ul>
</div>

<h2>교육/연수</h2>
<div class="cv-card">
  <div class="row">
    <strong>구디아카데미</strong> 클라우드(AWS) 활용 자바/스프링 부트캠프
    <span class="period">2025.03.04 ~ 2025.09.12</span>
  </div>
</div>

<h2>경력</h2>
<div class="cv-card">
  <ul class="timeline">
    <li>
      <div class="row">
        <strong>육군 중사</strong>
        <span class="period">2017.06 ~ 2024.05</span>
      </div>
      <div class="meta">인사·행정·환자 관리, 부대 운영지원</div>
    </li>
    <li>
      <div class="row">
        <strong>프로에스콤</strong> 보안팀 사원
        <span class="period">2024.10 ~ 2025.02</span>
      </div>
      <div class="meta">시설 보안·안전 관리</div>
    </li>
  </ul>
</div>

<h2>기술 역량</h2>
<div class="cv-card">
  <ul class="chips">
    <li><span class="chip">Java</span><em>팀 프로젝트 백엔드 핵심 로직 구현 (상)</em></li>
    <li><span class="chip">Spring Boot</span><em>REST API, 게시판·결제 모듈 (상)</em></li>
    <li><span class="chip">MyBatis</span><em>SQL 매퍼, 다중 JOIN (상)</em></li>
    <li><span class="chip">MySQL</span><em>DB 설계, ERD (상)</em></li>
  </ul>
</div>

<h2>자격증</h2>
<div class="cv-card">
  <ul class="list">
    <li><strong>SQL 개발자(SQLD)</strong>, 한국데이터산업진흥원 — 2025.06</li>
    <li><strong>실용수학자격 3급</strong>, 한국창의인성교육연구원 — 2016.06</li>
    <li><strong>E-Test Professionals</strong>, 한국창의인성교육연구원 — 2016.08</li>
  </ul>
</div>

<h2>프로젝트</h2>
<div class="cv-card">
  <ul class="links">
    <li><a href="/portfolio/lms/">학원용 LMS 시스템</a></li>
    <li><a href="/portfolio/b2b/">B2B 무역 구매·배송 서비스</a></li>
  </ul>
</div>

</div> <!-- /.cv-wrap -->

<style>
/* ------------------------------
   CV local theme (scoped)
   - 라이트/다크 모드 자동 대응
   - Minimal Mistakes/Academic Pages와 충돌 최소화
------------------------------ */

.cv-wrap{
  /* Light defaults */
  --bg: #ffffff;
  --text: #0f172a;     /* slate-900 */
  --muted:#6b7280;     /* gray-500 */
  --card:#ffffff;
  --border:#e5e7eb;    /* gray-200 */
  --accent:#16a34a;    /* green-600 */
  --accent-weak:#e8f7ec;
  --shadow: 0 6px 20px rgba(2, 6, 23, 0.06);
  color: var(--text);
}

@media (prefers-color-scheme: dark){
  .cv-wrap{
    --bg:#0b1220;      /* deep navy */
    --text:#e5e7eb;    /* gray-200 */
    --muted:#9ca3af;   /* gray-400 */
    --card:#0f172a;    /* slate-900 */
    --border:#1f2937;  /* slate-800 */
    --accent:#22c55e;  /* green-500 */
    --accent-weak:#0b2b17;
    --shadow: 0 10px 24px rgba(0,0,0,0.35);
  }
}
/* 테마 토글 플러그인 사용 시 클래스/속성 대응 */
html.dark .cv-wrap,
body.dark .cv-wrap,
[data-theme="dark"] .cv-wrap{
  --bg:#0b1220;
  --text:#e5e7eb;
  --muted:#9ca3af;
  --card:#0f172a;
  --border:#1f2937;
  --accent:#22c55e;
  --accent-weak:#0b2b17;
  --shadow: 0 10px 24px rgba(0,0,0,0.35);
}

.cv-wrap{
  background: var(--bg);
}
.cv-wrap h1, .cv-wrap h2, .cv-wrap h3{
  letter-spacing:-0.01em;
  line-height:1.25;
  margin-top: 0.6rem;
}
.cv-wrap h1{ font-size: clamp(1.6rem, 1.2rem + 1.2vw, 2.2rem); }
.cv-wrap h2{ font-size: clamp(1.25rem, 1.05rem + .8vw, 1.7rem); margin-top:2rem; }
.cv-wrap h3{ font-size: 1.1rem; margin-top:1.25rem; }

.cv-card{
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 16px 18px;
  margin: 14px 0 22px;
  box-shadow: var(--shadow);
}

/* 기본정보: 2열 그리드 */
.kv{
  display:grid;
  grid-template-columns: repeat(2, minmax(240px, 1fr));
  gap: 10px 18px;
}
.kv > div{ display:grid; grid-template-columns: 96px 1fr; align-items: baseline; gap: 8px; }
.kv dt{
  color: var(--muted);
  font-weight: 600;
}
.kv dd{
  margin:0;
  word-break: keep-all;
}

/* 타임라인 스타일 (학력/경력) */
.timeline{
  list-style:none; margin:0; padding:0;
}
.timeline li{
  padding: 10px 0 12px;
  border-bottom:1px dashed var(--border);
}
.timeline li:last-child{ border-bottom:none; }
.timeline .row{
  display:flex; justify-content: space-between; align-items: baseline; gap:12px; flex-wrap: wrap;
}
.timeline .period{
  font-size:.94rem; color: var(--muted);
}
.timeline .meta{
  color: var(--muted);
  margin-top: 4px;
}

/* 스킬 칩 */
.chips{
  list-style:none; margin:0; padding:0; display:grid; gap:10px;
}
.chips li{ display:flex; gap:10px; align-items:center; flex-wrap: wrap; }
.chip{
  display:inline-block;
  border:1px solid var(--accent);
  background: var(--accent-weak);
  color: var(--accent);
  padding: 3px 10px;
  border-radius: 999px;
  font-weight: 600;
  font-size: .92rem;
}
.chips em{
  font-style: normal;
  color: var(--muted);
}

/* 단순 리스트/링크 */
.list{ margin:0; padding-left: 18px; }
.links{ margin:0; padding-left: 18px; }
.links a{
  text-decoration: none;
  border-bottom: 1px solid transparent;
}
.links a:hover{
  border-color: var(--accent);
}

/* 반응형 */
@media (max-width: 720px){
  .kv{ grid-template-columns: 1fr; }
  .kv > div{ grid-template-columns: 88px 1fr; }
}
/* 1) 로컬 팔레트 강제 해제 → 상위(사이트) 색상에 맞춰 따라가게 */
.cv-wrap{
  --bg: inherit !important;
  --text: inherit !important;
  --muted: inherit !important;
  --card: inherit !important;
  --shadow: none !important;
}

/* 2) 카드 배경을 페이지 배경과 동일하게, 그림자 제거, 테두리만 아주 옅게 */
.cv-card{
  background: inherit !important;
  border-color: rgba(128,128,128,.25) !important; /* fallback */
  border-color: color-mix(in oklch, currentColor 18%, transparent) !important;
  box-shadow: none !important;
}

/* 3) 타임라인 구분선도 사이트 톤에 맞게 옅게 */
.timeline li{
  border-bottom-color: rgba(128,128,128,.25) !important; /* fallback */
  border-bottom-color: color-mix(in oklch, currentColor 18%, transparent) !important;
}

/* 4) 스킬 칩은 가독성만 살짝 유지(배경을 아주 약하게) */
.cv-card .chip{
  background: rgba(127,127,127,.08) !important; /* fallback */
  background: color-mix(in oklch, currentColor 8%, transparent) !important;
  border-color: rgba(127,127,127,.25) !important; /* fallback */
  border-color: color-mix(in oklch, currentColor 30%, transparent) !important;
  color: inherit !important;
}
</style>