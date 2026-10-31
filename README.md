# muse-skill

sungkil 맞춤 Muse 스킬 모음집 — 실제 사용 환경에서 검증하고, sungkil의 작업 방식에 맞게 최적화한 스킬들입니다.

## 스킬 목록

| 스킬 | 설명 |
|---|---|
| `ffmpeg-skill/` | 모든 영상·오디오 편집의 표준 도구. 자르기/합치기, 세로(9:16)·정사각 리프레임, 자막(SRT/ASS·karaoke), 음량 정규화(LUFS), BGM 덕킹, 플랫폼별 export(YouTube/Reels/TikTok). 편집 전 probe → `--dry-run --json` 계획 → 원본 보존 → 렌더 후 검증이 기본 절차. |
| `voice_dump_dispatch/` | 긴 음성 메모나 여러 작업이 섞인 메시지를 번호 목록으로 정리하고, 독립 작업은 병렬로 실행해 압축 보고 하나로 반환. |
| `video_production_sfx/` | 효과음 라이브러리 効果音ラボ(soundeffect-lab.info)에서 장면에 맞는 효과음을 골라 ffmpeg-skill로 믹싱하는 절차. |
| `account_connection_troubleshooting/` | 계정 연결이 막혔을 때 같은 링크를 반복하지 않고, 링크가 열린 방식(앱/브라우저)과 등록 vs 동의 단계를 먼저 진단. |

## sungkil 맞춤 최적화 포인트

- **속도 우선**: 확인용 질문을 최소화하고, 독립 작업은 같은 턴에 바로 시작 (voice_dump_dispatch의 "목록 먼저 확인" 단계 제거).
- **영상 편집 단일 경로**: 모든 영상/오디오 편집은 ffmpeg-skill로 통일. 플랫폼 템플릿은 `ffmpeg-skill/templates/` (reels, shorts, youtube, tiktok).
- **BGM 취향 반영**: 느리고 조용한 피아노보다 밝고 활기찬 음악을 기본값으로 (video_production_sfx).
- **공개 확인 원칙 유지**: 어떤 스킬도 게시·전송·구매 같은 공개/외부 행동을 sungkil의 항목별 확인 없이 실행하지 않음.

## 설치

스킬 폴더를 Muse 작업공간의 `~/workspace/custom-skills/` 아래에 복사하면 스킬 검색에 바로 잡힙니다.

```
cp -r voice_dump_dispatch ~/workspace/custom-skills/
```

## 출처 / 라이선스

- `ffmpeg-skill` — [kajisho5/ffmpeg-skill](https://github.com/kajisho5/ffmpeg-skill), MIT License (원본 `LICENSE` 포함).
- `voice_dump_dispatch` — [nanbada/muse-creative-skills](https://github.com/nanbada/muse-creative-skills) (MIT)를 이 환경에 맞게 개작.
- `video_production_sfx`, `account_connection_troubleshooting` — sungkil의 실제 작업에서 만든 자체 스킬.
