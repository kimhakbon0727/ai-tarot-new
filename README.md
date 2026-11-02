# ai-tarot-new

AI 타로 상담 new!!

- 사이트: https://ai-tarot-new.vercel.app
- 저장소: https://github.com/kimhakbon0727/ai-tarot-new

78장 타로 덱에서 카드를 직접 골라 뽑으면, 뽑힌 카드와 위치의 의미를 바탕으로 AI(Gemini)가 질문에 맞춰 해석해 주는 타로 상담 앱입니다.

## 구성

| 파일 | 설명 |
|------|------|
| `index.html` | 화면 전체(HTML/CSS/JS). 카드 78장 데이터와 SVG 일러스트 포함 |
| `api/tarot.js` | Vercel 서버리스 함수. Gemini API를 호출해 해석 생성 |
| `robots.txt` | 검색 로봇 설정 (`/api/` 수집 제외, 사이트맵 위치 안내) |
| `sitemap.xml` | 검색 포털에 알려줄 페이지 목록 |
| `google1d659d44e47dcdd4.html` | 구글 Search Console 소유권 확인 파일 (**삭제 금지, 수정 금지**) |

## 환경변수 (Vercel)

- `GEMINI_API_KEY` : Gemini API 키 (필수, 서버에서만 사용)
- `GEMINI_MODEL` : 사용할 모델명 (선택). 비워두면 코드의 기본값 사용

## 스프레드

- 원카드 (1장), 쓰리카드 (3장), 켈틱 크로스 (10장)
- 역방향 카드 포함 옵션 (포함 시 약 40% 확률로 역방향)

---

## 포털 사이트 등록 현황 (2026-11-02)

### 네이버 서치어드바이저

- [x] 사이트 등록: `https://ai-tarot-new.vercel.app`
- [x] 소유확인 완료 (HTML 태그 방식, `index.html`의 `<head>`에 `naver-site-verification` 메타태그)
- [x] robots.txt 수집 확인
- [x] 사이트맵 제출: `/sitemap.xml` (15:13)
- [x] 웹 페이지 수집 요청: `/` (15:13)
- [ ] 색인 확인: 서치어드바이저 > 검증 > 색인 상태 확인 (며칠 뒤)

### 구글 Search Console

- [x] 속성 추가: URL 접두어 `https://ai-tarot-new.vercel.app`
- [x] 소유권 확인 완료 (HTML 파일 방식, `google1d659d44e47dcdd4.html` 업로드)
- [x] 사이트맵 제출: `/sitemap.xml` (상태: 성공, 발견된 페이지 1개)
- [ ] 색인 생성 요청: 상단 검색창에 `https://ai-tarot-new.vercel.app/` 입력 > 색인 생성 요청
- [ ] 색인 확인: 왼쪽 메뉴 페이지, 또는 구글에서 `site:ai-tarot-new.vercel.app` 검색

> 소유확인과 사이트맵 제출은 검색 노출을 보장하지 않습니다. 신규 사이트는 색인에 며칠~몇 주 걸릴 수 있습니다.
> 네이버에서 `site:ai-tarot-new.vercel.app` 검색 시 아직 결과 없음 (등록 직후, 2026-11-02 15:16 기준)

---

## 등록 방법 상세

### A. 사전 준비 (저장소에 올릴 파일)

1. `robots.txt`와 `sitemap.xml`을 저장소 맨 위(`index.html`과 같은 위치)에 올립니다.
   - GitHub 저장소에서 **Add file > Upload files**로 올리고 **Commit changes**.
2. `index.html`의 `<head>`(`<title>` 아래)에 메타태그를 추가합니다.
   ```html
   <meta name="description" content="고민을 적고 78장 타로 덱에서 직접 카드를 골라보세요. 원카드·쓰리카드·켈틱 크로스 스프레드를 AI가 질문에 맞춰 해석해 주는 무료 AI 타로 상담.">
   <link rel="canonical" href="https://ai-tarot-new.vercel.app/">
   <meta property="og:type" content="website">
   <meta property="og:title" content="AI 타로 상담">
   <meta property="og:description" content="직접 카드를 고르면 AI가 질문에 맞춰 해석해 주는 타로 상담">
   <meta property="og:url" content="https://ai-tarot-new.vercel.app/">
   <meta property="og:locale" content="ko_KR">
   <meta name="naver-site-verification" content="(네이버에서 발급받은 값)" />
   ```
3. Vercel 배포가 끝날 때까지 1~2분 기다린 뒤 다음을 확인합니다.
   - 사이트에서 Ctrl+U(페이지 소스 보기)로 메타태그가 보이는지
   - `https://ai-tarot-new.vercel.app/robots.txt` 와 `/sitemap.xml`이 열리는지

> 중요: 소유확인 버튼은 **반드시 배포가 끝난 뒤** 눌러야 합니다. 배포 전에 누르면 "메타태그를 찾을 수 없습니다"로 실패합니다.

### B. 네이버 서치어드바이저 등록

1. https://searchadvisor.naver.com 에 네이버 계정으로 로그인합니다.
2. 오른쪽 위 **웹마스터 도구**를 누릅니다.
3. 사이트 등록 입력창에 `https://ai-tarot-new.vercel.app`을 넣고 추가합니다.
4. 소유확인 화면에서 **HTML 태그**를 선택하고, 나온 `<meta name="naver-site-verification" content="값" />`를 `index.html`의 `<head>`에 붙여넣습니다.
5. GitHub에 커밋하고 배포가 끝나면, 네이버 화면에서 **소유확인**을 누릅니다. "사이트 소유 확인이 완료되었습니다" 팝업이 나오면 성공입니다.
   - 태그 방식이 계속 실패하면 **HTML 파일 업로드** 방식(확인 파일을 받아 저장소 맨 위에 업로드)을 씁니다.
6. 사이트 목록에서 `https://ai-tarot-new.vercel.app`을 눌러 사이트 관리 화면으로 들어갑니다.
7. **요청 > 사이트맵 제출**: `https://ai-tarot-new.vercel.app/sitemap.xml` 입력 후 확인.
8. **요청 > 웹 페이지 수집**: `https://ai-tarot-new.vercel.app/` 입력 후 확인.
9. **검증 > robots.txt**에서 수집된 내용이 올린 파일과 같은지 확인합니다.
   - 아래 "robots.txt 간단 생성"으로 만든 파일을 다운로드해 덮어쓰지 않습니다 (`Disallow: /api/`와 `Sitemap` 줄이 빠짐).
10. 며칠 뒤 **검증 > 색인 상태 확인**, **검증 > URL 검사**에서 색인 여부를 확인합니다.

### C. 구글 Search Console 등록

1. https://search.google.com/search-console 에 구글 계정으로 로그인합니다.
2. 왼쪽 위 속성 선택 칸 > 맨 아래 **+ 속성 추가**를 누릅니다.
3. 오른쪽 **URL 접두어**에 `https://ai-tarot-new.vercel.app`을 입력하고 **계속**을 누릅니다. (도메인 방식은 DNS 설정이 필요해 `vercel.app`에는 맞지 않음)
4. 소유권 확인 화면의 **HTML 파일**에서 `google1d659d44e47dcdd4.html`을 다운로드합니다.
5. 받은 파일을 저장소 맨 위에 업로드하고 커밋합니다. 파일 이름과 내용은 수정하지 않습니다.
6. 배포 후 `https://ai-tarot-new.vercel.app/google1d659d44e47dcdd4.html`이 열리는지 확인하고, 소유권 확인 창에서 **확인**을 누릅니다.
   - 확인이 끝난 뒤에도 이 파일을 삭제하면 소유권이 풀리니 계속 둡니다.
   - (대안) **HTML 태그** 방식은 `<meta name="google-site-verification" content="값" />`를 `<head>`에 넣습니다.
7. 왼쪽 메뉴 **Sitemaps**에서 `sitemap.xml`을 입력하고 **제출**합니다. 상태가 **성공**이면 정상입니다.
8. 화면 위쪽 검색창에 `https://ai-tarot-new.vercel.app/`을 입력하고 Enter를 누른 뒤, **색인 생성 요청**을 누릅니다.
   - 처음에 "URL이 Google에 등록되어 있지 않음"이라고 나오는 것은 정상입니다.
9. 며칠 뒤 왼쪽 **페이지** 메뉴나 구글 검색창의 `site:ai-tarot-new.vercel.app`으로 색인 여부를 확인합니다.

### D. 색인이 됐는지 확인하는 법

- 네이버: 검색창에 `site:ai-tarot-new.vercel.app`, 또는 주소 `https://ai-tarot-new.vercel.app` 통째로 검색
- 구글: 검색창에 `site:ai-tarot-new.vercel.app`
- 포털 도구: 네이버 **검증 > 색인 상태 확인**, 구글 **페이지** 메뉴 (검색창보다 먼저 반영됨)

일주일이 지나도 나오지 않으면 도구 화면을 캡처해 원인(본문 텍스트 부족, 수집 오류 등)을 확인합니다.

---

## 검색 노출 개선 TODO

- [x] `<title>`, `<h1>`을 "AI 타로 상담"처럼 키워드가 들어가게 수정
- [x] 메인 화면에 보이는 소개 문단 추가 (설명서는 팝업 안에 숨겨져 있음)
- [ ] 개인정보처리방침 페이지 추가 (질문 내용이 Gemini로 전송됨을 명시)
- [ ] 커스텀 도메인 연결 (`vercel.app` 서브도메인은 신뢰도가 낮은 편)
- [ ] 고유한 서비스 이름 정하기 (검색어로 잡히기 쉽게)

## 운영 시 주의

- `/api/tarot`에 호출 제한이 없습니다. 방문자가 늘면 Gemini API 사용량과 비용이 늘 수 있으니 IP별 요청 제한, Google Cloud 쿼터 및 예산 알림 설정을 권장합니다.
- `GEMINI_MODEL`에 실제 사용 가능한 모델명이 들어 있는지 확인하세요. 모델명이 틀리면 해석이 오류로 나옵니다.
