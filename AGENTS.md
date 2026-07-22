# Visual Story Kit — AI 에이전트 작업 규칙

이 레포는 실행 코드가 아니라 AI 비주얼 스토리 제작용 문서 킷이다.
이 폴더에서 작업하는 에이전트는 아래 규칙을 따른다.

## 역할

사용자가 캐릭터 컨셉과 이야기를 주면, 이 레포의 템플릿을 채워
"이미지 생성 도구에 붙여넣기만 하면 되는 상태"까지 만든다.
이미지 생성 자체는 사용자가 외부 도구에서 직접 한다.

## 작업 순서 (순서 건너뛰기 금지)

1. **캐릭터 팩**: `characters/{캐릭터명}/profile.md` 생성.
   `character-system/character-pack-template.md` 구조를 그대로 따르고,
   완성 예시는 `characters/example-character/profile.md` 참고.
   팔레트는 반드시 hex 코드로 채운다.
2. **정면 마스터 프롬프트**: `character-system/four-view-reference-guide.md`
   Step 1 템플릿에 프로필을 채워 완성본을 사용자에게 전달.
   → 사용자가 이미지 승인할 때까지 대기 (게이트)
3. **4-view / 표정 / 포즈 시트 프롬프트**: 같은 가이드의 Step 2~4.
   → 사용자 승인 대기 (게이트)
4. **카드 플랜**: `prompt-system/planning-prompt.md`의 두 단계를 따른다.
   Step 1(스토리 플랜 + 캐릭터 목록) 승인 후에만 Step 2(카드 JSON) 진행.
   결과는 `examples/sample-episode/card-plan.json`과 같은 스키마의
   JSON으로 저장. `story-system/pacing-guide.md`의 검수 항목을 통과시킬 것.
5. **카드별 이미지 프롬프트**: `prompt-system/image-prompt.md` 형식으로 작성.
   예시는 `examples/sample-episode/image-prompts.md`.
6. **검수/재생성**: 사용자가 생성 결과를 공유하면
   `checklists/review-checklist.md` 게이트 4 기준으로 진단하고,
   실패 카드는 `prompt-system/regeneration-prompt.md`로 해당 카드만 재생성.

## 절대 규칙

- 캐릭터 외형 묘사는 캐릭터 팩에만 쓴다. 카드의 visual_prompt와
  이미지 프롬프트의 Card/Composition 부분에 외형을 반복하지 않는다.
- 모든 이미지 프롬프트에 아래 두 줄을 포함한다:
  - extract only the character identity from the attached reference images
  - ignore background, lighting, mood, and environment from the reference images
- 사용자에게 주는 프롬프트에 파일 경로를 넣지 않는다. 경로 대신
  프로필 내용을 직접 삽입하고, 레퍼런스 이미지는 첨부하라고 안내한다.
- 게이트(사용자 승인) 전에 다음 단계 산출물을 미리 만들지 않는다.
- 캔버스는 1080 x 1350, 핵심 요소는 1080 x 1080 safe area 안.
- 캐릭터 일관성 실패가 3장 이상이면 카드 재생성이 아니라
  4-view 레퍼런스 재제작을 제안한다.

## 산출물 저장 위치

```text
characters/{캐릭터명}/profile.md          # 캐릭터 팩
characters/{캐릭터명}/references/         # 승인된 레퍼런스 이미지 (사용자가 저장)
episodes/{에피소드명}/brief.md            # 브리프 + 스토리 플랜
episodes/{에피소드명}/card-plan.json      # 카드 플랜
episodes/{에피소드명}/image-prompts.md    # 카드별 완성 프롬프트
episodes/{에피소드명}/review-notes.md     # 검수 기록
```

`examples/`와 `characters/example-character/`는 참고용 예시이므로 수정하지 않는다.
