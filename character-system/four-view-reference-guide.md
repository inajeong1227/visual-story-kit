# 4-View 레퍼런스 가이드 (어라운드 뷰)

캐릭터를 여러 각도에서 고정한 시트입니다.
이 시트가 만들어진 뒤에는 모든 카드 생성 프롬프트에 레퍼런스로 첨부됩니다.

## 왜 한 장에 만드는가

각도별로 이미지를 따로 생성하면 매번 다른 캐릭터가 나옵니다.
반드시 한 이미지 안에 여러 뷰를 나란히 생성해야 모델이 일관성을 유지합니다.

## 제작 순서

```text
1. 캐릭터 팩의 프로필과 팔레트를 먼저 완성한다.
2. 정면 마스터 이미지 1장을 생성하고 승인한다.
3. 승인된 정면 마스터를 레퍼런스로 첨부해 4-view 시트를 생성한다.
4. 4-view를 검수하고 승인한다.
5. 같은 방식으로 표정 시트, 포즈 시트를 만든다.
```

처음부터 4방향을 한 번에 뽑지 않습니다. 정면이 먼저입니다.

## Step 1: 정면 마스터 프롬프트

```text
Create one master character reference image.

Character:
{character_profile}

Palette (exact hex):
{palette}

Rules:
- full body, front view, neutral A-pose
- neutral expression
- plain solid light gray background
- flat even lighting, no dramatic shadow
- full body visible, nothing cropped
- no text, no watermark
```

## Step 2: 4-View 시트 프롬프트

```text
Create one character turnaround sheet in a single image.

Reference:
- extract only the character identity from the attached reference image
- ignore background, lighting, mood, and environment from the reference

Character:
{character_profile}

Palette (exact hex):
{palette}

Layout:
- one horizontal row, 4 labeled views: FRONT / 3-4 VIEW / SIDE / BACK
- same character, same scale, same head height across all views
- neutral A-pose in every view
- neutral expression in every view
- same outfit and props in every view

Rules:
- plain solid light gray background
- flat even lighting
- full body visible in every view, nothing cropped
- no text except the view labels, no watermark
```

## Step 3: 표정 시트 프롬프트

```text
Create one expression sheet in a single image.

Reference:
- extract only the character identity from the attached turnaround sheet
- ignore background, lighting, mood, and environment from the reference

Layout:
- 3 x 3 grid, head and shoulders only
- expressions: neutral, happy, sad, angry, surprised, worried,
  embarrassed, determined, tired

Rules:
- same face shape, hairstyle, and palette in every cell
- plain solid background
- no text except expression labels, no watermark
```

## Step 4: 포즈 시트 프롬프트

포즈는 시리즈에서 자주 쓸 동작 위주로 6개 정도 고릅니다.
(예: 서 있기, 앉아 있기, 걷기, 스마트폰 보기, 손 흔들기, 놀라서 뒤돌기)

```text
Create one pose sheet in a single image.

Reference:
- extract only the character identity from the attached turnaround sheet
- ignore background, lighting, mood, and environment from the reference

Layout:
- 2 x 3 grid, full body in every cell
- poses: {pose_list}

Rules:
- same character identity, proportion, and palette in every cell
- neutral expression
- plain solid background
- no text, no watermark
```

## 검수 체크리스트

- [ ] 모든 뷰에서 머리 높이(키)가 같은가
- [ ] 모든 뷰에서 헤어스타일 실루엣이 같은가
- [ ] 후면 뷰의 머리색/의상 색이 정면과 같은가
- [ ] 의상 디테일(단추, 소품)이 뷰마다 사라지거나 생기지 않았는가
- [ ] 팔레트 hex와 눈으로 봤을 때 색이 일치하는가
- [ ] 배경이 단색인가 (분위기 배경이 섞이면 이후 생성이 오염됨)

실패한 뷰가 있으면 시트 전체를 재생성합니다.
4-view 시트만큼은 부분 수정보다 전체 재생성이 일관성에 안전합니다.

## 사용 규칙

카드 이미지를 생성할 때마다 프롬프트에 아래를 포함합니다.

```text
Reference:
- extract only the character identity from the attached reference images
- ignore background, lighting, mood, and environment from the reference images
```

이 두 줄이 없으면 모델이 레퍼런스의 배경과 조명까지 따라 해서
카드마다 분위기가 오염됩니다.
