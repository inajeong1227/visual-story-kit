# 기획 프롬프트 템플릿

브리프를 넣으면 카드 플랜을 구조화된 형식으로 뽑는 프롬프트입니다.
출력을 JSON으로 고정하면 카드 → 이미지 프롬프트 변환이 기계적으로 가능해집니다.

## Step 1: 브리프 → 스토리 플랜 + 캐릭터 추출

```text
You are planning a Korean instatoon carousel.

Brief:
- Audience: {audience}
- Goal: {goal}
- Topic: {topic}
- Format: {card_count} cards
- Tone: {tone}
- Constraints: {constraints}

Task 1. Write a story plan:
- beginning, middle, ending in 3 short Korean sentences
- follow this flow: hook -> situation -> feeling or problem
  -> turn -> interpretation -> closing

Task 2. Extract characters:
- list every character this story needs
- mark each as main or supporting
- for each character give: name, role in story, age range,
  3 personality keywords, 1-line appearance direction
- reuse existing characters if provided below, do not invent
  replacements for them

Existing characters:
{existing_character_packs_or_none}

Do not write card details yet. Wait for approval of the story plan
and character list.
```

여기서 멈추고 스토리 플랜과 캐릭터 목록을 승인합니다.
새 캐릭터가 나왔으면 카드 플랜 전에 캐릭터 팩부터 만듭니다.

## Step 2: 승인된 플랜 → 카드 플랜 JSON

```text
Using the approved story plan and characters, write the card plan.

Output valid JSON only, exactly this shape:

{
  "series_title": "",
  "tone": "",
  "visual_style": "",
  "cards": [
    {
      "index": 1,
      "role": "hook",
      "headline": "",
      "scene": "",
      "characters": [],
      "scene_ref": "",
      "narration": "",
      "dialogue": "",
      "caption": "",
      "visual_prompt": "",
      "regeneration_note": ""
    }
  ]
}

Rules:
- exactly {card_count} cards
- role must be one of: hook, situation, problem, turn,
  interpretation, closing
- one message per card
- headline: short, Korean, readable at thumbnail size
- scene: what is visually happening, one sentence
- characters: names from the approved character list only
- scene_ref: scene profile name if a fixed scene is used, else ""
- dialogue: max 2 speech bubbles per card
- visual_prompt: English, describes composition only,
  no character appearance details (the character pack handles that)
```

## visual_prompt에 외형을 쓰지 않는 이유

캐릭터 외형은 캐릭터 팩과 4-view 레퍼런스가 담당합니다.
카드 플랜의 visual_prompt에 외형 묘사가 섞이면 팩과 충돌해서
카드마다 캐릭터가 흔들립니다. visual_prompt는 구도, 행동,
카메라 거리, 감정만 씁니다.

## 검수 포인트

- [ ] 카드 수가 브리프와 일치하는가
- [ ] role 순서가 스토리보드 구조와 일치하는가
- [ ] 승인 목록에 없는 캐릭터가 등장하지 않는가
- [ ] visual_prompt에 외형 묘사가 섞여 있지 않은가
- [ ] 한 카드에 메시지가 하나인가

이 JSON이 승인되면 `image-prompt.md` 템플릿에 카드별로 채워 넣어
이미지 생성을 시작합니다.
