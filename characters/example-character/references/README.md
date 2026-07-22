# Mina Reference Notes

이 폴더에는 Mina의 승인된 레퍼런스 이미지를 저장합니다.
현재 저장소에는 이미지 파일을 포함하지 않고, 필요한 파일명과 제작 순서만 안내합니다.

## Expected Files

```text
master-front.png   # 승인된 정면 마스터 이미지
four-view.png      # FRONT / 3-4 VIEW / SIDE / BACK 시트
expressions.png    # 표정 시트
poses.png          # 포즈 시트
```

## Creation Order

1. `profile.md`의 캐릭터 프로필과 hex 팔레트를 완성합니다.
2. `character-system/four-view-reference-guide.md`의 정면 마스터 프롬프트로 `master-front.png`를 만듭니다.
3. 정면 마스터를 승인한 뒤 4-view 시트를 만듭니다.
4. 4-view가 승인되면 표정 시트와 포즈 시트를 만듭니다.
5. 카드 이미지를 생성할 때마다 4-view, 표정 시트, 포즈 시트를 레퍼런스로 첨부합니다.

## Reference Rule

카드 생성 프롬프트에는 항상 아래 규칙을 포함합니다.

```text
Extract only the character identity from reference images.
Ignore background, lighting, mood, and environment unless explicitly requested.
```
