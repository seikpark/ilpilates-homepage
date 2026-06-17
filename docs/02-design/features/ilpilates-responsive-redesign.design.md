# ilpilates-responsive-redesign - Design Document (Starter)

> Version: 1.0.0 | Date: 2026-06-17 | Status: Complete
> Level: Starter | Plan: `docs/01-plan/features/ilpilates-responsive-redesign.plan.md`

---

## 1. Overview

IL Pilates 홈페이지의 기존 콘텐츠와 이미지 자산을 유지하면서, 모바일 우선 흐름과 데스크톱 편집형 레이아웃을 강화한다. 핵심 방향은 "차분한 프라이빗 필라테스 스튜디오"이며, 사진이 먼저 말하고 텍스트가 짧게 받쳐주는 디자인을 목표로 한다.

이번 디자인은 기존 정보 구조를 크게 바꾸지 않는다. 대신 hero, method, studio, equipment, detail, teacher, review, closing 섹션 사이의 리듬을 정리하고, 모바일에서는 스크롤 진행이 자연스럽게 이어지며, PC에서는 화면 폭을 활용한 비대칭 구성과 sticky editorial cue를 만든다.

## 2. Page Structure

| Section | Anchor | Purpose | Mobile Behavior | Desktop Behavior |
|---------|--------|---------|-----------------|------------------|
| Header | `#top` | 로고, 메뉴, 문의 진입 | sticky header + hamburger | sticky header + inline nav + CTA |
| Hero | `#top` | 브랜드 첫인상과 문의 CTA | full-viewport image, text lower-left, sticky booking CTA | full-viewport image, large editorial headline |
| Method | `#method` | 수업 방식과 3단계 흐름 | intro copy + stacked rhythm steps | two-column editorial head + horizontal steps |
| Studio | `#studio` | 스튜디오 신뢰와 분위기 | image first, copy below | image/copy split with generous whitespace |
| Equipment | none | 장비 보유와 준비 상태 | horizontal snap gallery | asymmetric grid gallery |
| Studio Details | none | 전체 이미지 자산 활용과 공간 디테일 | horizontal snap mosaic | 6-column editorial mosaic |
| Teachers | `#teachers` | 강사 소개 | swipeable teacher cards | two-column teacher layout |
| Reviews | `#reviews` | 리뷰와 신뢰 확보 | review image + swipeable cards | image/copy split + two-column reviews |
| Closing / Footer | `#contact` | 마지막 문의 유도와 소셜 링크 | strong CTA + sticky button | editorial closing band + footer columns |

## 3. Design

### 3.1 Layout

#### Mobile First

- Header height는 64px로 유지하고, 로고와 메뉴 버튼이 안정적으로 터치되게 한다.
- Hero는 첫 화면 대부분을 이미지로 채우되, 텍스트는 이미지 하단의 안정적인 영역에 배치한다.
- 주요 CTA는 hero 내부 `CONTACT / INSTAGRAM`과 하단 sticky `Book a consult`로 중복 배치해 모바일 전환 동선을 줄인다.
- Gallery, Teachers, Reviews, Details는 모바일에서 가로 스냅 흐름을 유지한다.
- 불필요한 장식 텍스트나 설명성 문구는 화면에 추가하지 않는다.

#### Desktop

- Header는 72px 높이의 고정 내비게이션으로 유지한다.
- Hero headline은 좌측 하단에서 크고 강하게 보여주되, 이미지 피사체와 겹쳐도 읽히는 수준의 대비를 유지한다.
- Section header는 `section-index`와 heading이 분리된 two-column editorial grid를 사용한다.
- Equipment와 Studio Details는 단순 카드 나열이 아니라 이미지 크기 차이를 가진 비대칭 그리드로 구성한다.
- Reviews는 좌측 이미지와 우측 리뷰 카드로 나누어 사회적 증거를 한 번에 파악하게 한다.

### 3.2 Styling

#### Tokens

| Token | Value | Use |
|-------|-------|-----|
| `--ink` | `#111111` | headings, body, solid CTA |
| `--paper` | `#ffffff` | page background |
| `--mist` | `#f4f6f3` | quiet section background |
| `--sage` | `#647363` | section labels, calm brand accent |
| `--rose` | `#cfa79b` | low-frequency movement accent |
| `--line` | `rgba(17, 17, 17, 0.18)` | subtle dividers |
| `--muted` | `rgba(17, 17, 17, 0.58)` | secondary copy |

#### Typography

- Font family: `Pretendard Variable`, `Pretendard`, system sans fallback.
- Hero H1: mobile 38px, tablet 62px, desktop 82px.
- Section H2: mobile 31px, tablet 42px.
- Body copy: 15-16px, line-height 1.5-1.62.
- Letter spacing은 0으로 유지한다.

#### Shape & Depth

- Cards use radius 6px or less.
- No heavy shadows.
- Images remain flat and editorial.
- CTA uses black/white inversion and small radius.

### 3.3 Planned Design Improvements

1. Add a compact `session-strip` after hero to turn "Assessment first / Customized sessions" into a more structured mobile-friendly cue.
2. Add a visual `movement-line` inside Method so the 3-step flow feels guided rather than listed.
3. Strengthen desktop section composition with slightly more pronounced editorial grids and image hover motion.
4. Improve CTA rhythm by making `CONTACT` and `INSTAGRAM` labels consistent across hero, closing, and footer.
5. Keep all existing core copy, but refine awkward wording where it improves trust and tone.

## 4. Components

| Component | Source | Behavior |
|-----------|--------|----------|
| `site-header` | HTML/CSS/JS | sticky nav, hamburger toggles `is-open` |
| `hero` | HTML/CSS | full-viewport image, responsive headline, CTA |
| `session-strip` | HTML/CSS | compact trust cues below hero, mobile stacked or horizontal |
| `section-head` | HTML/CSS | section index + heading editorial layout |
| `flow-steps` | HTML/CSS | 3-step method explanation |
| `snap-gallery` | HTML/CSS | mobile horizontal snap, desktop grid |
| `detail-mosaic` | HTML/CSS | mobile snap, desktop mosaic |
| `teacher-card` | HTML/CSS | instructor card with image and copy |
| `review-item` | HTML/CSS | customer review card |
| `mobile-sticky-cta` | HTML/CSS | fixed mobile consultation CTA |

## 5. Content Guidance

### Preserve

- "Transform Your Body. Elevate Your Mind."
- Method / Studio / Teachers / Reviews / Contact navigation
- Instructor names and credentials
- Review author names and core review meanings
- Contact email and Instagram link
- All image assets

### Improve Carefully

- Replace overly generic copy with clearer Pilates-specific phrasing.
- Keep the tone calm, professional, and personal.
- Avoid aggressive sales copy, exclamation-heavy phrasing, or urgency marketing.
- Keep English body copy unless the section already contains Korean review text.

## 6. Implementation Order

1. Add `session-strip` markup after hero.
2. Refine hero and method copy only where tone becomes clearer.
3. Update CSS tokens/section rhythm for mobile and desktop.
4. Add hover/focus states for galleries and CTAs without adding heavy motion.
5. Re-run syntax/image checks.
6. Capture full viewport mobile and desktop screenshots. Do not use cropped screenshots.
7. Commit, push, and verify GitHub Pages.

## 7. Test Plan

| Check | Command / Method | Expected |
|-------|------------------|----------|
| JS syntax | `node --check script.js` | pass |
| Image usage | Node script over `images/` references | all 19 images referenced |
| Broken copy tokens | `rg` for placeholder text, typos, and stale cache versions | no unexpected matches |
| Local render | `python3 -m http.server` + Chrome headless full viewport | nonblank mobile/desktop screenshots |
| Deployment | `curl -I -L https://seikpark.github.io/ilpilates-homepage/` | HTTP 200 |

## 8. Deployment

- Repository: `https://github.com/seikpark/ilpilates-homepage`
- Pages URL: `https://seikpark.github.io/ilpilates-homepage/`
- Source: `main` branch, root path `/`

## 9. Learning Points

- PDCA 문서는 실제 구현 전에 범위와 성공 기준을 고정해, "디자인을 더 예쁘게" 같은 모호한 요청을 검수 가능한 작업으로 바꾼다.
- 정적 사이트에서도 모바일/데스크톱을 별도 결과물처럼 다루면 품질이 올라간다.
- 모든 이미지 사용 조건은 단순 삽입이 아니라 섹션 리듬과 정보 계층 안에서 해결해야 한다.

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0.0 | 2026-06-17 | Initial PDCA design for IL Pilates responsive redesign | Codex |
