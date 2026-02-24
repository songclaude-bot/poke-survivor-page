# 프로젝트 소개 페이지 템플릿

이 템플릿은 songclaude-bot 퍼블릭 프로젝트 소개 페이지용입니다.
private 서비스 코드와는 별개로, 프로젝트를 설명하고 허브에서 연결되는 **공개 페이지**를 빠르게 만들 수 있습니다.

---

## 사용법

### 1. 새 repo 생성

```bash
gh repo create songclaude-bot/{{프로젝트명}} --public --clone
```

### 2. 템플릿 복사

```bash
cp -r project-page-template/* 새_repo/
cp project-page-template/.github 새_repo/ -r
```

### 3. index.html 커스텀

`{{PLACEHOLDER}}` 형식의 값들을 모두 교체하세요:

| 플레이스홀더 | 설명 | 예시 |
|---|---|---|
| `{{PROJECT_TITLE}}` | `<title>` 태그 | `OKKO in OKKY — 해커톤 후기` |
| `{{BADGE_TEXT}}` | 히어로 상단 뱃지 | `Hackathon Retrospective` |
| `{{PROJECT_NAME}}` | 메인 타이틀 | `OKKO in OKKY` |
| `{{SUBTITLE}}` | 부제목 | `OKKY 제1회 AI 바이브코딩 미니 해커톤` |
| `{{META_1~3}}` | 키워드 (2~4개 조절) | `2026.02.21`, `4시간`, `우수상` |

### 4. 챕터 구성

- 기본 챕터 1개가 활성화되어 있고, 나머지(인용구, 기술스택, 타임라인, 이미지그리드)는 주석 처리
- 프로젝트 성격에 맞게 필요한 블록을 주석 해제 & 커스텀
- 챕터 번호와 slug를 순서대로 매기세요: `chapter 01 — the beginning`

### 5. 이미지

- `images/` 폴더에 넣기
- `loading="lazy"` 유지
- `img-grid`로 2열 배치 가능 (모바일은 자동 1열)

### 6. 서비스 링크

- 실제 서비스가 있다면 footer에 링크 추가 (주석 해제)
- Home 링크는 항상 허브(`songclaude-bot.github.io`)를 가리킴

---

## 구조

```
repo/
├── index.html          ← 메인 페이지 (이 파일만 수정)
├── images/             ← 이미지 폴더
├── CLAUDE.md           ← 이 가이드 (배포 시 제외됨)
└── .github/
    └── workflows/
        └── pages.yml   ← GitHub Pages 자동 배포
```

---

## 체크리스트

새 프로젝트 페이지를 만들 때:

- [ ] repo 생성 (public)
- [ ] 템플릿 복사 & 플레이스홀더 교체
- [ ] 챕터 구성 (내용, 이미지 추가)
- [ ] Pages 활성화: `gh api repos/songclaude-bot/REPO_NAME/pages -X POST -f "build_type=workflow" -f "source[branch]=main" -f "source[path]=/"`
- [ ] push & 배포 확인
- [ ] 허브 페이지에 별 추가 (`songclaude-bot.github.io/index.html`)

---

## 디자인 규칙

이 템플릿은 글로벌 가이드라인(`.github` repo의 CLAUDE.md)의 디자인 시스템을 따릅니다.
색상, 폰트, 애니메이션을 변경하지 마세요. 통일된 우주 감성이 핵심입니다.

레퍼런스: https://songclaude-bot.github.io
