# 이미지 프롬프트 템플릿

아래 템플릿은 카드별 이미지 생성 전에 사용합니다.

```text
Create one Korean visual story card for Instagram carousel.

Canvas:
- 1080 x 1350 px vertical feed canvas
- keep key text and character inside a 1080 x 1080 safe area

Series:
- Title: {series_title}
- Tone: {tone}
- Visual style: {visual_style}

Character lock:
{character_profile}

Card:
- Index: {card_index}
- Role: {card_role}
- Headline: {headline}
- Scene: {scene}
- Narration: {narration}
- Dialogue: {dialogue}
- Caption: {caption}
- Background: {background}

Rules:
- keep the same character identity as the reference
- simple Korean instatoon composition
- one message per card
- readable text, no tiny paragraphs
- simple background
- no watermark
- no brand logo unless explicitly requested
- do not change hairstyle, age, or body proportion
```
