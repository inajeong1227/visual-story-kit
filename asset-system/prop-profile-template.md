# 소품 프로필 템플릿

캐릭터의 정체성에 붙어 다니는 소품, 스토리상 중요한 소품은 고정값으로 관리합니다.
(예: 항상 들고 다니는 텀블러, 목에 건 사원증, 특정 색 노트북)

배경에 한 번 지나가는 소품까지 만들 필요는 없습니다.
"이 소품이 다르게 그려지면 독자가 눈치채는가"가 기준입니다.

## 저장 규약

```text
assets/
  props/
    {prop_name}/
      profile.md            # 이 템플릿을 채운 문서
      reference.png         # 승인된 소품 레퍼런스 이미지 (필요 시)
```

## 1. 기본 정보

- 소품 이름:
- 소유 캐릭터: (캐릭터 팩 경로)
- 역할: (정체성 소품 / 스토리 소품 / 개그 소품)

## 2. 고정 외형

- 형태:
- 크기 기준: (캐릭터 손/얼굴 대비 상대 크기로 적기)
- 색 (hex): `#______`
- 디테일: (로고 없음, 스티커 1개 등 — 2개 이내로)

## 3. 등장 규칙

- 반드시 함께 나오는 상황:
- 나오면 안 되는 상황:
- 잡는 손 / 착용 위치 기본값:

## 4. 의상 연속성 메모

의상도 소품과 같은 방식으로 관리합니다.

- 기본 의상은 캐릭터 팩에서 고정합니다.
- 에피소드에서 옷이 바뀌면(잠옷, 외출복 등) 그 에피소드 문서에
  "이 에피소드의 의상: {설명} + hex"를 명시하고 전 카드에 동일 적용합니다.
- 카드 중간에 의상이 바뀌는 것은 스토리상 이유가 있을 때만 허용합니다.

## 소품 레퍼런스 프롬프트 (필요 시)

```text
Create one prop reference image.

Prop:
{prop_profile}

Rules:
- prop only, no character
- 2 views in one image: front view and 3-4 view
- exact color: {hex}
- plain solid background
- flat instatoon style matching the series
- no text, no watermark
```
