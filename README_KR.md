# Claude Code Spinner Words

[Claude Code](https://docs.anthropic.com/en/docs/claude-code)에서 로딩할 때 나오는 재미있는 문구들, 궁금하지 않으셨나요?

이 도구는 Claude Code CLI 바이너리에서 모든 스피너 단어를 추출하고, 버전별 마크다운 파일로 저장하여 변경 이력을 추적합니다.

> [English (영어)](README.md)

## 작동 방식

1. 시스템에 설치된 Claude Code 바이너리를 찾습니다
2. `strings` 명령어로 바이너리에서 출력 가능한 텍스트를 추출합니다
3. 시드 기반 부트스트래핑으로 스피너 단어 배열을 찾습니다 — *Flibbertigibbeting*, *Razzmatazzing* 같은 희귀 단어를 이용해 정확한 위치를 특정합니다
4. 동명사(-ing) 형태의 단어를 파싱하여 `words/<버전>.md`에 저장합니다
5. 이전 추출 결과와의 diff를 보여줘서 버전 간 추가/삭제된 단어를 확인할 수 있습니다

## 사용법

```bash
python3 extract_spinner_words.py
```

출력 예시:

```
Binary:  /Users/you/.local/share/claude/versions/2.1.63
Version: 2.1.63
Seeds:   192 words (12 built-in)
Running strings...

Extracted 192 spinner words:

    1. Accomplishing
    2. Actioning
    3. Actualizing
  ...
  192. Zigzagging

Saved to words/2.1.63.md
```

## 요구 사항

- Python 3.10+
- Claude Code CLI 설치 필요
- `strings` 명령어 사용 가능 (macOS/Linux에 기본 포함)

## 프로젝트 구조

```
.
├── extract_spinner_words.py   # 메인 추출 스크립트
└── words/
    └── 2.1.63.md              # 버전별 추출된 단어 목록
```

## 주요 단어 예시

v2.1.63에서 발견된 192개 스피너 단어 중 일부 하이라이트:

| | | | |
|---|---|---|---|
| Beboppin' | Flibbertigibbeting | Razzmatazzing | Discombobulating |
| Canoodling | Lollygagging | Shenaniganing | Tomfoolering |
| Clauding | Flambéing | Sautéing | Prestidigitating |
| Moonwalking | Spelunking | Hullaballooing | Whatchamacalliting |

## 라이선스

MIT
