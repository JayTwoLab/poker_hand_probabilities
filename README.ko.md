### `poker_hand_probabilities` : 포커(`Poker`) 확률 계산기

> [English](README.md) , [Korean](README.ko.md)

이 프로젝트는 포커 게임의 다양한 손패(hand)에 대한 확률을 계산하는 Python 프로그램입니다. 기본적인 카드 덱에서 특정 카드를 제외하거나 추가할 수 있으며, 이에 따른 확률 변화도 분석할 수 있습니다.  

---

#### 주요 기능

1. **포커 확률 계산**  
   52장의 기본 카드 덱을 사용하여 아래의 손패 확률을 계산합니다:
   - `High Card` (하이 카드)
   - `One Pair` (원 페어)
   - `Two Pair`(투 페어)
   - `Three of a Kind` (트리플)
   - `Straight` (스트레이트)
   - `Flush` (플러쉬)
   - `Full House` (풀하우스)
   - `Four of a Kind` (포카드)
   - `Straight Flush` (스트레이트 플러쉬)
   - `Royal Straight Flush` (로얄 스트레이트 플러쉬)  

2. **카드 제외 및 추가**  
   - 특정 카드를 덱에서 제외하거나 새로운 카드를 추가하여 확률을 다시 계산할 수 있습니다.
   - 예: 퀸(Q) 4장을 제외하거나 에이스(A) 4장을 추가한 경우의 확률 계산.

3. **사용법**  
   - `calculate_poker_probabilities` 함수는 입력받은 제외 카드 또는 추가 카드를 고려하여 확률을 반환합니다.
   - `main` 함수는 여러 시나리오(기본 덱, 카드 제외, 카드 추가)에 따른 확률을 출력합니다.

---

#### 코드 예시

```python
# 기본 52장 덱의 확률 계산
probabilities = calculate_poker_probabilities()

# 퀸(Q) 4장 제외
excluded_cards = ["QH", "QD", "QC", "QS"]
probabilities_excluded = calculate_poker_probabilities(excluded_cards=excluded_cards)

# 에이스 4장 추가
added_cards = ["Extra_A1", "Extra_A2", "Extra_A3", "Extra_A4"]
probabilities_added = calculate_poker_probabilities(added_cards=added_cards)
```

- 결과
```
--- Full Deck (52 cards) ---
High Card: 50.117739%
One Pair: 42.256903%
Two Pair: 4.753902%
Three of a Kind: 2.112845%
Straight: 0.392465%
Flush: 0.196540%
Full House: 0.144058%
Four of a Kind: 0.024010%
Straight Flush: 0.001539%
Royal Flush: 0.000154%

--- Excluding QH, QD, QC, QS ---
High Card: 24.291014%
One Pair: 64.138144%
Two Pair: 7.215541%
Three of a Kind: 3.206907%
Straight: 0.595689%
Flush: 0.298312%
Full House: 0.218653%
Four of a Kind: 0.033405%
Straight Flush: 0.002336%
Royal Flush: 0.000234%

--- Adding 4 extra Aces ---
High Card: 66.059308%
One Pair: 28.751123%
Two Pair: 3.234501%
Three of a Kind: 1.437556%
Straight: 0.267029%
Flush: 0.133724%
Full House: 0.098015%
Four of a Kind: 0.017697%
Straight Flush: 0.001047%
Royal Flush: 0.000105%
```

---

#### 실행 방법

1. Python 3.x 이상이 설치된 환경에서 사용 가능합니다.
2. 아래 명령어로 프로그램을 실행하세요:
   ```bash
   python poker.py
   ```
3. 실행 시 각 시나리오에 따른 확률이 출력됩니다.

---

#### 기여 및 라이선스

- **기여**: 이 프로젝트에 대한 피드백 및 기여를 환영합니다. Pull Request를 통해 수정 사항을 제안해주세요.
- **라이선스**: 본 프로젝트는 자유롭게 사용할 수 있는 [MIT License](https://opensource.org/licenses/MIT)를 따릅니다.
