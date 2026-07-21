# 장면 프로필 템플릿

반복해서 등장하는 장소는 캐릭터처럼 고정값으로 관리합니다.
같은 "우리 집 거실"이 카드마다 다른 집이 되는 것을 막습니다.

## 저장 규약

```text
assets/
  scenes/
    {scene_name}/
      profile.md            # 이 템플릿을 채운 문서
      reference.png         # 승인된 장면 레퍼런스 이미지
```

## 1. 기본 정보

- 장면 이름:
- 용도: (일상 배경 / 사건 장소 / 상징 공간)
- 등장 빈도: (매 에피소드 / 특정 에피소드만)

## 2. 고정 요소

- 공간 종류: (거실, 사무실, 카페, 길거리 등)
- 시점 기본값: (정면, 살짝 위에서, 눈높이 등)
- 핵심 지형지물: (창문 위치, 소파, 책상 등 3개 이내)
- 시간대 기본값: (낮 / 저녁 / 밤)

## 3. 컬러 팔레트 (hex)

- 벽/배경 메인: `#______`
- 바닥/하단: `#______`
- 포인트 색: `#______`

## 4. 밀도 규칙

- 배경 밀도: (선 몇 개 수준의 미니멀 / 가구 실루엣 정도 / 디테일)
- 캐릭터보다 배경이 눈에 띄면 실패입니다.

## 5. 반드시 유지할 것

- 핵심 지형지물의 위치 관계
- 팔레트
- 밀도 수준

## 6. 바뀌어도 되는 것

- 카메라 거리 (와이드 / 미디엄 / 클로즈업)
- 시간대 (스토리상 필요할 때)
- 소품의 등장 여부

## 장면 레퍼런스 프롬프트

```text
Create one scene reference image for a Korean instatoon series.

Scene:
{scene_profile}

Palette (exact hex):
{palette}

Rules:
- no characters in this image
- simple flat instatoon background style
- minimal detail, the scene must stay behind characters
- flat even lighting
- no text, no watermark
```

카드 생성 시에는 캐릭터 레퍼런스와 함께 이 장면 레퍼런스를 첨부하고,
"use this scene reference for the background only"라고 명시합니다.
