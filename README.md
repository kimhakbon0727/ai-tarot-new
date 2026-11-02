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

## 환경변수 (Vercel)

- `GEMINI_API_KEY` : Gemini API 키 (필수, 서버에서만 사용)
- `GEMINI_MODEL` : 사용할 모델명 (선택). 비워두면 코드의 기본값 사용

## 스프레드

- 원카드 (1장), 쓰리카드 (3장), 켈틱 크로스 (10장)
- 역방향 카드 포함 옵션 (포함 시 약 40% 확률로 역방향)

## 포털 사이트 등록 기록 (2026-11-02)

### 네이버 서치어드바이저

- [x] 사이트 등록: `https://ai-tarot-new.vercel.app`
- [x] 소유확인 완료 (HTML 태그 방식)
  - `index.html`의 `<head>`에 `naver-site-verification` 메타태그 추가
- [x] robots.txt 수집 확인 (검증 > robots.txt)
- [ ] 사이트맵 제출: `https://ai-tarot-new.vercel.app/sitemap.xml`
- [ ] 웹 페이지 수집 요청: `https://ai-tarot-new.vercel.app/`
- [ ] 색인 확인: 서치어드바이저 > 검증 > 색인 상태 확인
- 참고: 소유확인은 검색 노출을 보장하지 않습니다. 신규 사이트는 색인에 며칠~몇 주 걸릴 수 있습니다.
- 네이버에서 `site:ai-tarot-new.vercel.app` 검색 시 아직 결과 없음 (등록 직후, 2026-11-02 15:16 기준)

### 구글 Search Console

- [ ] 속성 추가 (URL 접두어)
- [ ] 소유 확인 (HTML 태그, `google-site-verification`)
- [ ] 사이트맵 제출

## 검색 노출 개선 TODO

- [ ] `<title>`, `<h1>`을 "AI 타로 상담"처럼 키워드가 들어가게 수정
- [ ] 메인 화면에 보이는 소개 문단 추가 (설명서는 팝업 안에 숨겨져 있음)
- [ ] 개인정보처리방침 페이지 추가 (질문 내용이 Gemini로 전송됨을 명시)
- [ ] 커스텀 도메인 연결 (`vercel.app` 서브도메인은 신뢰도가 낮은 편)
- [ ] 고유한 서비스 이름 정하기 (검색어로 잡히기 쉽게)

## 운영 시 주의

- `/api/tarot`에 호출 제한이 없습니다. 방문자가 늘면 Gemini API 사용량과 비용이 늘 수 있으니 IP별 요청 제한, Google Cloud 쿼터 및 예산 알림 설정을 권장합니다.
- `GEMINI_MODEL`에 실제 사용 가능한 모델명이 들어 있는지 확인하세요. 모델명이 틀리면 해석이 오류로 나옵니다.
