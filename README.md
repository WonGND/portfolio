# portfolio

곽원용 — 전장 디스플레이 HW설계 엔지니어 포트폴리오.

- **웹**: GitHub Pages로 호스팅되는 단일 페이지 (`index.html`)
- **PDF**: 페이지 우측 하단 "PDF로 저장" 버튼 (또는 브라우저 인쇄 → PDF 저장) 으로 A4 인쇄용 문서 생성

## 구조

```
portfolio/
├── index.html                        # 포트폴리오 본문 (내용 수정은 이 파일에서)
└── .github/workflows/deploy-pages.yml  # main 푸시 시 GitHub Pages 자동 배포
```

## 내용 수정 방법

`index.html` 안에 `[수정 포인트]` 주석이 달린 위치만 고치면 됩니다.

- 연락처: `<header>` 내 `.contact` 부분
- AI 툴 상세: "대표 프로젝트" 섹션의 주석 처리된 목록 형식 참고

## 배포

- 공개 주소: **https://wongnd.github.io/portfolio/**
- `main` 브랜치에 푸시하면 GitHub Actions가 `gh-pages` 브랜치로 동기화하고, Pages가 자동으로 재배포합니다.
- 반영까지 보통 1~2분 걸립니다.

---

이 포트폴리오는 Claude Code로 제작되었습니다.
