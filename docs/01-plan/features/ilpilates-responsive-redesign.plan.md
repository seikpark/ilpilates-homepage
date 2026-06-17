# ilpilates-responsive-redesign - Plan Document

> Version: 1.0.0 | Date: 2026-06-17 | Status: Complete
> Level: Starter

---

## 1. Overview

### 1.1 Purpose

기존 IL Pilates 정적 홈페이지를 PDCA 흐름으로 재정의하고, 모바일 우선 경험을 유지하면서 데스크톱에서도 충분히 정교하게 보이는 반응형 디자인으로 개선한다.

### 1.2 Background

현재 사이트는 GitHub Pages에 배포된 단일 페이지 정적 홈페이지다. 모든 이미지 자산은 이미 사용 중이며, 로고와 파비콘도 `images/logo.png`를 기준으로 적용되어 있다. 이번 단계에서는 기존 정보 구조와 핵심 문구를 해치지 않는 선에서 화면의 리듬, 섹션 전환, 모바일 탐색성, 데스크톱 편집감(editorial feel)을 강화한다.

## 2. Goals

### 2.1 Primary Goals

- [x] PDCA Plan 문서를 작성해 범위와 성공 기준을 명확히 한다.
- [x] PDCA Design 문서를 작성할 수 있는 전제 조건을 마련한다.
- [ ] 모바일 첫 화면에서 핵심 메시지, 문의 CTA, 로고 인지가 안정적으로 보이게 한다.
- [ ] PC 버전에서 단순 나열형 섹션이 아니라 잡지형 편집 레이아웃처럼 보이게 한다.
- [ ] 기존 문장 톤을 유지하되, 어색하거나 반복적인 표현은 더 자연스럽게 다듬는다.
- [ ] `/images` 내 19개 이미지 자산을 계속 모두 사용한다.
- [ ] GitHub Pages 배포 상태를 유지한다.

### 2.2 Non-Goals

- Wix 사이트의 CMS 또는 예약 시스템을 새로 구현하지 않는다.
- 새로운 백엔드, 데이터베이스, 결제 기능을 추가하지 않는다.
- 기존 리뷰, 강사, 장비, 연락처 정보의 의미를 바꾸지 않는다.
- 사용자가 제공하지 않은 외부 이미지나 브랜드 자산을 추가하지 않는다.

## 3. Scope

### 3.1 In Scope

- 단일 페이지 `index.html` 구조 개선
- `styles.css` 기반 모바일/태블릿/데스크톱 반응형 디자인 개선
- 필요한 경우 `script.js`의 경량 인터랙션 개선
- Plan/Design 문서 생성
- 최종 검수: 이미지 참조, JS 문법, 모바일/데스크톱 렌더링, Git 상태

### 3.2 Out of Scope

- 커스텀 도메인 연결
- 다국어 전환 기능
- 예약 폼, 결제, 회원 기능
- SEO 장문 콘텐츠 확장
- 새로운 프레임워크 도입

## 4. Requirements

### 4.1 Functional Requirements

| ID | Requirement | Priority | Status |
|----|-------------|----------|--------|
| FR-01 | 사용자는 모바일 첫 화면에서 스튜디오 정체성과 문의 CTA를 바로 인지해야 한다. | High | Planned |
| FR-02 | 사용자는 헤더 내 메뉴로 Method, Studio, Teachers, Reviews, Contact 섹션에 이동할 수 있어야 한다. | High | Existing |
| FR-03 | 모든 이미지 자산 19개는 사이트 어디선가 실제로 참조되어야 한다. | High | Existing |
| FR-04 | 로고와 파비콘은 `images/logo.png`를 사용해야 한다. | High | Existing |
| FR-05 | 모바일에서는 가로 스냅 갤러리로 이미지 탐색이 쉬워야 한다. | Medium | Existing |
| FR-06 | 데스크톱에서는 섹션별 이미지와 텍스트의 비율이 넓은 화면에 맞게 재배치되어야 한다. | High | Planned |

### 4.2 Non-Functional Requirements

| Category | Criteria | Measurement Method |
|----------|----------|-------------------|
| Responsiveness | 390px 모바일과 1440px 데스크톱에서 주요 텍스트 겹침이 없어야 한다. | 전체 뷰포트 스크린샷 검수 |
| Performance | 별도 빌드 과정 없이 GitHub Pages에서 정적 파일로 로드되어야 한다. | `curl -I`, 브라우저 렌더링 |
| Accessibility | 메뉴 버튼 `aria-expanded`, 이미지 대체 텍스트, 의미 있는 섹션 heading을 유지한다. | 코드 검토 |
| Maintainability | HTML/CSS/JS 3파일 중심 구조를 유지하고 새 의존성을 추가하지 않는다. | 파일 구조 검토 |
| Brand Fit | 29CM 참고 스타일의 절제된 타이포그래피, 흰 여백, 낮은 radius, 사진 중심 구성을 유지한다. | 디자인 문서 기준 검토 |

## 5. Success Criteria

- [ ] Plan 문서가 `docs/01-plan/features/ilpilates-responsive-redesign.plan.md`에 존재한다.
- [ ] Design 문서가 `docs/02-design/features/ilpilates-responsive-redesign.design.md`에 존재한다.
- [ ] 변경 후 `node --check script.js`가 통과한다.
- [ ] `/images` 내 19개 이미지가 모두 참조된다.
- [ ] 모바일 전체 뷰포트 스크린샷에서 hero, CTA, header가 자연스럽다.
- [ ] 데스크톱 전체 뷰포트 스크린샷에서 hero와 주요 섹션이 과도하게 비어 보이지 않는다.
- [ ] GitHub Pages 배포 URL이 HTTP 200으로 응답한다.

## 6. Schedule

| Phase | Target Date | Status |
|-------|------------|--------|
| Plan | 2026-06-17 | Complete |
| Design | 2026-06-17 | In Progress |
| Implementation | 2026-06-17 | Pending |
| Review | 2026-06-17 | Pending |

## 7. Risks & Mitigations

| Risk | Impact | Probability | Mitigation |
|------|--------|-------------|------------|
| 모바일 hero에 텍스트와 이미지 피사체가 겹쳐 가독성이 떨어질 수 있음 | High | Medium | 텍스트 위치, 배경 오버레이, CTA 높이를 모바일 기준으로 먼저 검수한다. |
| 모든 이미지를 사용하려다 섹션이 다시 나열식으로 보일 수 있음 | Medium | Medium | 이미지 사용은 유지하되, 모바일은 스냅 흐름, 데스크톱은 모자이크/편집형 그리드로 구성한다. |
| 디자인 문서와 실제 코드가 어긋날 수 있음 | Medium | Low | 구현 전 Design 문서를 먼저 작성하고, 구현 후 요구사항별 체크를 수행한다. |
| GitHub Pages 캐시로 최신 CSS가 늦게 반영될 수 있음 | Low | Medium | CSS/JS 버전 쿼리를 갱신한다. |

## 8. Architecture Considerations

### 8.1 Project Level Selection

| Level | Characteristics | Selected |
|-------|-----------------|:--------:|
| Starter | Simple structure, static sites | Yes |
| Dynamic | Feature-based modules, BaaS integration | No |
| Enterprise | Strict layer separation, microservices | No |

### 8.2 Key Architectural Decisions

| Decision | Options | Selected | Rationale |
|----------|---------|----------|-----------|
| Framework | Plain HTML / React / Next.js | Plain HTML | 현재 사이트는 정적 홈페이지이며 빠른 배포와 유지보수에 충분하다. |
| Styling | Plain CSS / Tailwind / CSS Modules | Plain CSS | 기존 구조를 유지하고 의존성을 늘리지 않는다. |
| Interactions | Vanilla JS / Library | Vanilla JS | 메뉴, reveal 정도의 경량 인터랙션만 필요하다. |
| Deployment | GitHub Pages / Vercel | GitHub Pages | 이미 신규 GitHub 프로젝트로 배포되어 있다. |

## 9. References

- Design style guide: `DESIGN.md`
- Source files: `index.html`, `styles.css`, `script.js`
- Image assets: `images/`
- Deployment: `https://seikpark.github.io/ilpilates-homepage/`

## 10. Next Steps

1. [x] Plan 문서 작성
2. [ ] Design 문서 작성
3. [ ] Design 문서 기준으로 HTML/CSS/JS 개선
4. [ ] 모바일/데스크톱 검수
5. [ ] GitHub Pages 업데이트

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0.0 | 2026-06-17 | Initial PDCA plan for responsive redesign | Codex |
