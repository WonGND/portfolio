# portfolio

곽원용 — 전장 디스플레이 HW설계 엔지니어 포트폴리오.

- **웹**: GitHub Pages로 호스팅되는 정적 사이트
- **PDF**: 각 페이지의 "PDF로 저장" 버튼 (브라우저 인쇄 → PDF 저장) 으로 A4 문서 생성

## 구조

```
portfolio/
├── index.html                # 포트폴리오 메인 (KPI · 역량 육각형 · STAR 프로젝트 · 경력)
├── cover-letter.html         # 자기소개서 페이지 (틀 — 본문은 아래 md에서 로드)
├── encrypt.html              # 비공개 섹션 암호화 도구 (소유자용, 링크 비노출)
├── content/
│   ├── cover-letter.md       # ★ 자기소개서 본문 (내용 수정은 이 파일만)
│   └── private.enc.json      # 비공개 섹션(이직 사유) 암호문 — 암호 없이는 읽을 수 없음
└── .github/workflows/deploy-pages.yml  # main 푸시 시 gh-pages로 자동 배포
```

## 내용 수정 방법 (소유자 전용)

수정 권한은 이 저장소에 커밋할 수 있는 사람 = 저장소 소유자에게만 있습니다.
사이트의 "✏️ 수정" 버튼이 GitHub 편집 화면을 열어주며, 로그인·권한이 없으면 저장할 수 없습니다.

- **자기소개서**: `content/cover-letter.md` 를 GitHub 웹 편집기(연필 아이콘)에서 수정 → Commit.
  마크다운 문법(`##` 제목, `**굵게**`, `-` 목록)만 알면 되고, `<!-- -->` 주석은 사이트에 표시되지 않습니다.
- **포트폴리오 본문**: `index.html` 안의 `[수정 포인트]` 주석 위치를 수정.
  역량 육각형 차트의 축·수치는 `index.html`의 `SKILLS` 배열에서 수정.
- **비공개 섹션(이직 사유)**: 본문이 `content/private.enc.json`에 AES-256-GCM으로 암호화되어 있어
  저장소가 public이어도 암호 없이는 읽을 수 없습니다. 수정/암호 변경은
  사이트의 `/encrypt.html` 페이지에서: 새 암호+본문 입력 → 생성된 JSON을
  `content/private.enc.json`에 붙여넣고 Commit. (내용은 브라우저 밖으로 전송되지 않음)
- 커밋하면 1~2분 내 사이트에 자동 반영됩니다.

## 배포

- 공개 주소: **https://wongnd.github.io/portfolio/**
- `main` 브랜치에 푸시하면 GitHub Actions가 `gh-pages` 브랜치로 동기화하고, Pages가 자동으로 재배포합니다.
- 반영까지 보통 1~2분 걸립니다.

## URL(저장소 이름/도메인) 변경 시 체크리스트

사이트 내부 링크는 전부 상대경로라 URL이 바뀌어도 그대로 동작합니다. 아래만 확인하세요.

1. **저장소 이름 변경** (Settings → General → Rename): Pages 주소가 `wongnd.github.io/<새이름>/` 으로 자동 변경됨.
2. `cover-letter.html` 상단 스크립트의 `var REPO = "WonGND/portfolio"` 를 새 이름으로 수정 (✏️ 수정 버튼 링크용).
3. `index.html` 푸터의 "사이트 수정" 링크 주소 수정.
4. 이 README의 공개 주소 갱신.
5. **커스텀 도메인**을 쓸 경우: Settings → Pages → Custom domain 에 도메인 입력 (저장소에 `CNAME` 파일이 자동 생성됨). 1~4는 동일.

---

이 포트폴리오는 Claude Code로 제작되었습니다.
