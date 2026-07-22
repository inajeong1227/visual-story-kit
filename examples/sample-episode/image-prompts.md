# Sample Episode Image Prompts

아래 프롬프트는 `card-plan.json`을 `prompt-system/image-prompt.md` 형식에 맞춰 옮긴 예시입니다.
실제 생성 전에는 Mina의 4-view, 표정 시트, 포즈 시트를 레퍼런스로 첨부합니다.

주의: 프롬프트 안의 `characters/example-character/profile.md` 같은 파일 경로는
이미지 생성 도구가 읽지 못합니다. 실제로 붙여넣을 때는 경로 대신
프로필 문서의 내용을 직접 넣고, 레퍼런스 이미지를 파일로 첨부하세요.

## Shared Reference Rule

모든 카드 프롬프트에 아래 규칙을 포함합니다.

```text
Reference:
- extract only the character identity from the attached reference images
- ignore background, lighting, mood, and environment from the reference images
```

## Card 1 Prompt

```text
Create one Korean visual story card for Instagram carousel.

Canvas:
- 1080 x 1350 px vertical feed canvas
- keep key text and character inside a 1080 x 1080 safe area

Series:
- Title: 캐릭터가 매번 달라지는 이유
- Tone: 담백한 공감형, 약간 웃김
- Visual style: simple Korean instatoon, rounded hand-drawn line, flat colors, minimal background

Character lock:
- Use Mina from characters/example-character/profile.md
- Do not change hairstyle, age, body proportion, outfit color, or overall drawing style

Card:
- Index: 1
- Role: hook
- Headline: AI 캐릭터가 왜 매번 다를까?
- Scene: Mina looks at six generated character cards spread on a desk, each card looking slightly different.
- Dialogue: 분명 같은 캐릭터였는데...

Composition:
- Close-up desk composition
- Six small image cards spread out
- Mina leaning in with a confused expression
- Simple white background
- Large empty top area for headline

Rules:
- one message per card
- readable text, no tiny paragraphs
- simple background
- no watermark
- no brand logo unless explicitly requested
```

## Card 4 Prompt

```text
Create one Korean visual story card for Instagram carousel.

Canvas:
- 1080 x 1350 px vertical feed canvas
- keep key text and character inside a 1080 x 1080 safe area

Series:
- Title: 캐릭터가 매번 달라지는 이유
- Tone: 담백한 공감형, 약간 웃김
- Visual style: simple Korean instatoon, rounded hand-drawn line, flat colors, minimal background

Character lock:
- Use Mina from characters/example-character/profile.md
- Do not change hairstyle, age, body proportion, outfit color, or overall drawing style

Card:
- Index: 4
- Role: turn
- Headline: 먼저 고정해야 하는 건 프롬프트가 아니었다
- Scene: Mina places a character pack document before the image cards.
- Narration: 먼저 필요한 건 캐릭터 팩이었다.
- Dialogue: 아, 기준표부터 만들자.

Composition:
- Mina holds up a simple document labeled Character Pack
- Image cards are pushed to the side
- Brighter background than card 3
- Character Pack document is the visual center

Rules:
- one message per card
- readable text, no tiny paragraphs
- simple background
- no watermark
- no brand logo unless explicitly requested
```

## Why Only Two Full Prompts?

샘플에서는 모든 카드의 전체 프롬프트를 반복하지 않습니다.
실제 작업에서는 `card-plan.json`의 각 카드를 `prompt-system/image-prompt.md`에 넣어 같은 형식으로 확장합니다.
