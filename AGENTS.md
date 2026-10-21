# 개인 홈페이지 작업 안내

이 저장소는 `Jaewook-L/Jaewook-L.github.io`의 Academic Pages 기반 Jekyll 사이트이며, 공개 주소는 `https://jaewook-l.github.io/`이다. 사용자가 한국어로 제공하는 수정 지시나 문구를 실제 소스 변경으로 이어서 처리한다. 사용자의 최신 지시와 요청 범위를 우선한다.

## 작업 원칙

- 작업 전 Git 상태를 확인하고 기존 사용자 변경을 보존한다.
- 기존 디자인, 영문 콘텐츠의 문체, permalink를 유지하며 요청한 범위만 수정한다. 제목이나 파일명을 바꾸어도 기존 공개 URL을 임의로 바꾸지 않는다.
- 연구 실적, 저자 순서, 출판 상태, 날짜, 소속은 제공된 근거대로 반영하며 추측해서 보완하지 않는다.
- 단순 파악이나 로컬 환경 설정 요청을 공개 콘텐츠 변경 또는 배포 요청으로 해석하지 않는다.
- 필요한 작업을 자율적으로 진행하고 불필요한 확인 절차를 추가하지 않는다. 이후 명시적으로 요청된 수정·배포는 해당 요청 범위에 따라 수행한다.

## 소스 위치

| 수정 대상 | 파일 |
| --- | --- |
| 홈 소개, 학력, 경력 | `_pages/about.md` |
| 사이드바 소개, 사진, 이메일, 학술 링크 | `_config.yml`의 `author`, `images/JWL_picture.jpg` |
| 연구 설명과 관련 논문 목록 | `_pages/research.md` |
| 논문 정보 | `_publications/*.md` |
| 논문 목록 분류와 정렬 | `_pages/publications.html` |
| 논문 목록 항목과 개별 상세 | `_includes/archive-single.html`, `_layouts/single.html` |
| 학회 발표 정보와 목록 | `_talks/*.md`, `_pages/talks.html` |
| 발표 항목과 상세 | `_includes/archive-single-talk.html`, `_layouts/talk.html` |
| 연락처 | `_pages/contact.md` |
| 상단 메뉴 | `_data/navigation.yml` |
| 논문·연구 그림, 설명, 캡션 | `_data/figures.yml`, `images/publications/`, `images/research/` |
| 그림 마크업과 배치 | `_includes/content-figure.html`, `_sass/layout/_figures.scss` |
| 색상, 글꼴, 간격, 반응형 | `_sass/_themes.scss`, `_sass/theme/`, `_sass/layout/` |
| 스타일 진입점 | `assets/css/main.scss` |
| 공통 페이지 구성 | `_layouts/default.html`, `_includes/head*`, `_includes/footer*` |
| JavaScript | `assets/js/_main.js`, `assets/js/plugins/`, `assets/js/theme.js` |

## 콘텐츠 일관성

- 논문의 내부 정렬과 상태 분류에는 `category`, `authorship`, `venue`를 사용한다. `venue`의 `Under Review`, `In Revision`, `In Preparation`은 정확한 문자열로 분류된다. `category: manuscripts`이면서 `authorship: first` 또는 `co-first`인 저널 논문은 각 연도에서 먼저 배치하고, 나머지 항목은 그 아래에 배치한다. 저자 역할과 출판 유형에 따른 구분 제목은 화면에 표시하지 않는다.
- Accepted 논문은 저널명을 `venue`에 넣고 `status: accepted`, citation, 링크를 함께 확인한다. 기존 상세 처리와 편집 예시는 `README.md`에 있다.
- 사용자의 지속적인 선호(2026-10-21): Publications의 출판·accepted 항목 전체를 `date` 연도로 자동 분류하고 최신 연도부터 접기/펼치기로 표시하며 기본 상태는 닫힘이다. 각 연도 안에서는 First / Co-first 저널 논문을 먼저 배치하고 공동저자·북챕터·기타 항목을 그 아래에 함께 배치한다. First / Co-first, Co-authored, Book Chapters, Other Publications 구분 제목 없이 하나의 목록으로 표시한다. 준비 중·심사 중 항목은 연도 목록과 구분한 별도 상태 목록을 유지한다.
- 연도 옆 `4 publications` 같은 개수와 `Select a year...` 안내는 표시하지 않는다. 준비 중·심사 중·공동저자·북챕터·기타 항목을 포함한 전체 목록에 번호를 붙이며 화면의 마지막 항목이 1번이 되도록 위쪽으로 연속 번호를 붙인다. 논문 추가 시 연도와 번호를 자동 계산하며 템플릿에 직접 적지 않는다.
- In Preparation과 연도별 목록은 공통 서식을 사용한다. 논문 제목의 글자 크기는 `.publications-list` 공통 스타일에서 지정하고, 접기 제목의 여백은 `.publication-section`에서 통일한다. 상태나 연도에 따라 논문 제목 크기를 다르게 적용하지 않는다.
- 각 연도에서 먼저 배치하는 First / Co-first 그룹과 그 아래의 나머지 그룹은 각각 `date` 내림차순이며, 준비 중·심사 중 상태 목록도 `date` 내림차순이다. `_config.yml`의 `future: true` 때문에 미래 날짜도 노출되므로 날짜를 임의로 현재 날짜에 맞추지 않는다.
- Research의 Related Publications는 `_data/research_publications.yml`의 논문 ID를 통해 `_publications/*.md`의 제목·저널·연도를 직접 읽는다. 제목은 논문 원본 파일 한 곳에서 수정한다. 출판된 제목에 실질적인 차이가 있으면 DOI/공식 출판사 정보로 확인하고, 미출판 논문은 사용자가 제공한 최신 제목을 따른다. 새 논문을 Research에 연결할 때 해당 연구 분야의 ID 목록에 파일명 stem을 추가한다.
- 논문 상세의 기존 permalink는 주로 `/publication/...`이다. 컬렉션 기본 경로 `/publications/...`와 혼동하지 않는다.
- `_data/figures.yml`의 논문 key는 해당 Markdown 파일명에서 `.md`를 뺀 값과 대소문자까지 일치해야 한다. `image: ""`는 그림을 숨긴다. 그림 교체 시 경로와 alt를 함께 확인하고 원본 내용을 자르지 않는다.
- 소속·연락처 변경은 `_config.yml`, `_pages/about.md`, `_pages/contact.md`의 중복 표기를 함께 확인한다.
- 메뉴에서 제외한 페이지도 빌드될 수 있다. 기존 예제 페이지나 자료를 별도 요청 없이 일괄 삭제하지 않는다.

## 로컬 작업과 검증

환경 상태와 설치 안내는 `local/SETUP.md`, 운영 명령은 `local/site.ps1`을 확인한다. Ruby 설치나 GitHub 인증이 완료되어 있다고 가정하지 않는다.

```powershell
powershell -ExecutionPolicy Bypass -File .\local\site.ps1 -Action Check
powershell -ExecutionPolicy Bypass -File .\local\site.ps1 -Action Build
powershell -ExecutionPolicy Bypass -File .\local\site.ps1 -Action Serve
```

- YAML front matter, Liquid 문법, 관련 링크·이미지 경로와 Git diff를 변경 범위에 맞춰 확인한다.
- 빌드 가능한 환경이면 Jekyll Build로 검증한다. 디자인·배치·동작을 바꿨다면 로컬 미리보기에서 해당 페이지와 모바일 폭을 확인한다.
- 작은 문구 변경에 구현을 그대로 반복하는 테스트를 새로 만들지 않는다. 검증을 실행하지 못했다면 그 한계를 명확히 알린다.
- `_config.yml` 변경 후에는 실행 중인 Jekyll 서버를 재시작한다.
- `assets/js/_main.js` 또는 번들에 포함된 플러그인을 수정하면 `npm run build:js`로 `assets/js/main.min.js`도 갱신한다. 공개 페이지는 이 번들을 읽으며 배포 workflow에는 npm 빌드 단계가 없다.
- 생성된 `_site/`, 의존성, 캐시를 소스로 커밋하지 않는다. 로컬 운영 자료는 배포 제외된 `local/`에 둔다.

## 배포

- `.github/workflows/pages.yml`은 `master` push 또는 수동 실행으로 Jekyll 빌드 후 GitHub Pages에 배포한다. `master` push는 공개 사이트에 영향을 준다.
- 배포는 사용자가 요청한 범위에 맞춰 수행한다. 로컬 저장, Git 커밋, 원격 push, 배포 성공을 구분해서 보고한다.
- 배포를 수행했다면 Actions 결과와 실제 공개 페이지의 변경 반영을 확인한다. 인증 또는 권한이 없으면 성공한 것으로 보고하지 않는다.
- `_talks/**`, `talks/**`, `talkmap.ipynb` 변경 시 `.github/workflows/scrape_talks.yml`도 실행되어 지도 생성 결과를 자동 commit/push할 수 있다. 발표 수정 후 원격의 추가 커밋 여부를 확인한다.
