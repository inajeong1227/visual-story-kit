# Sample Episode Review Notes

이 문서는 샘플 에피소드의 검수 기준을 보여주는 예시입니다.

## Gate 1: Story Plan + Character List

- [ ] 대상이 명확한가: AI로 카드형 콘텐츠를 만들고 싶은 사람
- [ ] 문제 상황이 명확한가: 캐릭터가 매번 다르게 보임
- [ ] 해결 방향이 명확한가: 캐릭터 팩과 레퍼런스를 먼저 승인함
- [ ] 새 캐릭터가 필요한가: 아니오, Mina 사용

## Gate 2: Card Plan

- [ ] 카드 수가 6장인가
- [ ] role 순서가 hook -> situation -> problem -> turn -> interpretation -> closing인가
- [ ] 한 카드에 메시지가 하나인가
- [ ] visual_prompt에 Mina의 외형 설명이 반복되지 않았는가
- [ ] 카드 4에서 시각적 전환이 느껴지는가

## Gate 3: References

- [ ] Mina의 정면 마스터가 승인됐는가
- [ ] 4-view 시트가 승인됐는가
- [ ] 표정 시트와 포즈 시트가 준비됐는가
- [ ] 레퍼런스 배경이 카드 배경에 새어 들어오지 않도록 프롬프트에 명시했는가

## Gate 4: Card Images

카드마다 확인합니다.

- [ ] Mina가 같은 캐릭터로 보이는가
- [ ] 헤어스타일, 얼굴형, 옷 색이 유지되는가
- [ ] 핵심 문장과 캐릭터가 1080 x 1080 safe area 안에 있는가
- [ ] 텍스트가 너무 작지 않은가
- [ ] 배경이 캐릭터보다 튀지 않는가
- [ ] 다음 카드로 넘기고 싶은 리듬이 있는가

## Regeneration Examples

```text
Regenerate only card 3.

Keep:
- same story role: problem
- same message: character identity is drifting
- same Mina character identity

Fix:
- make the three character variations easier to compare
- reduce background detail
- keep all comparison points inside the 1080 x 1080 safe area

Do not change:
- Mina's short bob
- lavender shirt
- simple Korean instatoon style
```
