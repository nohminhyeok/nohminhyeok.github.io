---
title: "B2B 무역 구매·배송 서비스"
collection: portfolio
permalink: /portfolio/b2b/
excerpt: "파이널 팀 프로젝트<br/><img src='/images/final.png'>"
---

<p><strong>기간</strong>: 2025.07.25 ~ 2025.09.09<br>
<strong>역할</strong>: 주문·결제 / 견적서 / 계약 모듈</p>

<p><strong>주요 구현</strong><br>
결제(카카오페이 API, 주소 API), 주문 조회 상세, 견적서, 계약(전자서명·PDF),
공휴일 API 일정/대금 입력</p>

<p><strong>GitHub</strong>:
  <a href="https://github.com/freestyle-y/final_project_b2b" target="_blank" rel="noopener">
    freestyle-y
  </a>
</p>
<p><strong>사이트 바로가기</strong>:
  <a href="http://3.36.133.135:9000/" target="_blank" rel="noopener">
	B2B
  </a>
</p>

---

## 프로젝트 개요
<p><strong>목표</strong>: B2B 해외구매·배송 흐름을 한 시스템에서 견적→계약→결제→컨테이너/배송까지 이어지도록 구현</p>
<p><strong>성과</strong>: 주문·결제 트랜잭션 정리, 전자서명/첨부파일 일원화, 공휴일 API로 일정/대금 계산 자동화</p>
<p><strong>팀/기간</strong>: 4인, 2025.07.25 ~ 2025.09.09</p>

---

## 담당 역할 & 기여도
- **결제/주문**: 카카오페이 Ready/Approve 플로우, 주문/포인트/배송지 저장 및 롤백 지점 명확화
- **견적/계약**: 전자서명 DataURL 저장(파일화)→PDF 반영, 계약상태/대금 스케줄 관리
- **조회/관리**: 주문 상세, 배송조회 링크(운송장/컨테이너 정보), 관리자 목록(DataTables)
- **문서화**: 테이블 정의·요구사항·회의록 정리, 화면설계서 반영

---

## 데이터 모델(ERD)
<p><img src="/assets/docs/b2b/4. ERD_Y조(B2B 무역).png" alt="B2B ERD" loading="lazy"></p>

---

## 핵심 기능
- <strong>주문/결제</strong>: 장바구니/주문 생성, 포인트 사용/적립, 카카오페이 결제, 실패/취소 처리
- <strong>견적/계약</strong>: 견적서 작성/승인, 계약서 전자서명(공급자/수요자), 계약 PDF 다운로드
- <strong>물류</strong>: 컨테이너 등록/상태, 배송현황 표시, 회수/완료 처리
- <strong>관리자 UI</strong>: 페이징/정렬/검색, 엑셀 내보내기, 멀티 헤더 테이블

---

## 문제 해결 사례
<p><strong>① 카카오페이 흐름 정합성</strong><br>
문제: 주문·포인트 저장, 결제 Ready/Approve 간 타이밍 이슈로 중복 승인/실패 롤백 혼선<br>
접근: <em>주문/결제/포인트</em> 선저장 → Ready 응답으로 TID/redirect 저장 → 승인 시 <em>상태 전이</em>(성공/실패) 일원화, 트랜잭션 경계 재정의<br>
결과: 재시도/취소 케이스에서도 데이터 정합성 유지</p>

<p><strong>② FK 제약으로 컨테이너 삭제 실패</strong><br>
문제: <code>Cannot delete or update a parent row</code> (contract_delivery→container FK)<br>
접근: 배송 레코드 존재 시 <em>논리삭제(use_status)</em> 또는 <em>상태 전이</em>만 허용, 물리삭제는 참조 없을 때만 수행(서비스 레벨 가드)<br>
결과: 물류 이력 무결성 보존, 예외/500 제거</p>

<p><strong>③ 포인트 사용 합계가 3배로 차감</strong><br>
문제: reward_history를 order와 조인 시 상품 수만큼 곱연산 발생<br>
접근: <code>SUM(DISTINCT ...)</code> 대신 <code>reward_history</code>에서 <em>그룹 합</em>을 먼저 구하고 주문 기준으로 조인, 또는 <em>서브쿼리</em>로 단일 스칼라 값 추출<br>
결과: 실제 사용액과 일치, 음수/중복 차감 방지</p>

<p><strong>④ use_status 모호성 에러</strong><br>
문제: 다중 테이블 조인에서 <code>Column 'use_status' in where clause is ambiguous</code><br>
접근: 모든 컬럼을 <code>테이블별 별칭</code>으로 완전수식, Mapper XML의 where절 정리<br>
결과: 쿼리 안정성/가독성 개선</p>

---

## 산출물(다운로드/보기)
<ul class="doc-list">
  <li><a href="/assets/docs/b2b/1. WBS_Y조(B2B무역).xlsx">1. WBS_Y조(B2B무역).xlsx</a></li>
  <li><a href="/assets/docs/b2b/2. 요구사항 정의서_Y조(B2B 무역).xlsx">2. 요구사항 정의서_Y조(B2B 무역).xlsx</a></li>
  <li><a href="/assets/docs/b2b/3. 테이블 정의서_Y조(B2B 무역).xlsx">3. 테이블 정의서_Y조(B2B 무역).xlsx</a></li>
  <li>
    <a href="/assets/docs/b2b/4. ERD_Y조(B2B 무역).png" target="_blank" rel="noopener">
      4. ERD_Y조(B2B 무역).png
    </a>
  </li>

  <li><a href="/assets/docs/b2b/5. 화면설계서_Y조(B2B 무역).pptx">5. 화면설계서_Y조(B2B무역).pptx</a></li>
  <li><a href="/assets/docs/b2b/7. 발표 PPT_Y조(B2B 무역).pptx">6. 발표 PPT_Y조(B2B 무역).pptx</a></li>
</ul>

---

## 시연 영상
<div class="video">
  <iframe
    src="https://www.youtube.com/embed/USnFH2vjaoQ"
    title="B2B 프로젝트 시연영상"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen></iframe>
</div>

---

## 향후 개선
- 결제 실패/취소 리커버리 UX(최근 시도 재개), 중복 승인 방어 강화
- 계약 이력/서명 감사 로그, 첨부 파일 버저닝
- 배송 단계 웹훅/알림(메일/슬랙) 자동화, 컨테이너 ETA 예측
- 대용량 대비 쿼리 튜닝/캐싱, 비동기 이벤트 도입

<style>
.video{position:relative;padding-bottom:56.25%;height:0;overflow:hidden}
.video iframe{position:absolute;top:0;left:0;width:100%;height:100%}
.doc-list{margin:0;padding-left:1.2rem}
.doc-list li{margin:.2rem 0}
.note{font-size:.9rem;color:#666}
</style>
