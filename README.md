# `poker_hand_probabilities` : Poker Hand Probabilities

## Code

```python
# -*- coding: utf-8 -*-
# poker.py

from math import comb

def calculate_poker_probabilities(excluded_cards=None, added_cards=None):
    # All cards and excluded cards, plus added card settings
    # :kr: 전체 카드와 제외된 카드, 추가된 카드 설정
    total_cards = 52
    if excluded_cards:
        total_cards -= len(excluded_cards)
    if added_cards:
        total_cards += len(added_cards)

    # 5 possible card combinations
    # :kr: 가능한 다섯 장 카드 조합
    total_combinations = comb(total_cards, 5)

    # Defining probability calculation functions
    # :kr: 확률 계산 함수 정의
    def high_card():
        return total_combinations - one_pair() - two_pair() - three_of_a_kind() - straight() - flush() - full_house() - four_of_a_kind() - straight_flush()

    def one_pair():
        return comb(13, 1) * comb(4, 2) * comb(12, 3) * (4 ** 3)

    def two_pair():
        return comb(13, 2) * (comb(4, 2) ** 2) * comb(11, 1) * 4

    def three_of_a_kind():
        return comb(13, 1) * comb(4, 3) * comb(12, 2) * (4 ** 2)

    def straight():
        return 10 * (4 ** 5 - 4)
    # 10 straight combinations, excluding the same suit
    # :kr: 텐 스트레이트 조합, 같은 슈트 제외

    def flush():
        return comb(4, 1) * (comb(13, 5) - 10)
    # Exclude Straight from Flush
    # :kr: 플러시에서 스트레이트 제외

    def full_house():
        return comb(13, 1) * comb(4, 3) * comb(12, 1) * comb(4, 2)

    def four_of_a_kind():
        return comb(13, 1) * comb(4, 4) * comb(total_cards - 4, 1)

    def straight_flush():
        return 10 * 4

    def royal_flush():
        return 4
    # One from each of the four suits
    # :kr: 4개의 슈트에서 하나씩

    # Save calculated probability
    # :kr: 계산된 확률 저장
    probabilities = {
        "High Card": high_card() / total_combinations * 100,
        "One Pair": one_pair() / total_combinations * 100,
        "Two Pair": two_pair() / total_combinations * 100,
        "Three of a Kind": three_of_a_kind() / total_combinations * 100,
        "Straight": straight() / total_combinations * 100,
        "Flush": flush() / total_combinations * 100,
        "Full House": full_house() / total_combinations * 100,
        "Four of a Kind": four_of_a_kind() / total_combinations * 100,
        "Straight Flush": straight_flush() / total_combinations * 100,
        "Royal Flush": royal_flush() / total_combinations * 100
    }

    return probabilities

def main():
    # Use 52 cards in full
    # :kr: 52장 카드 전체 사용
    print("--- Full Deck (52 cards) ---")
    probabilities_full_deck = calculate_poker_probabilities()
    for hand, prob in probabilities_full_deck.items():
        print(f"{hand}: {prob:.6f}%")

    # Exclude some cards (e.g. 4 Q)
    # :kr: 일부 카드 제외 (예: 퀸 네 장)
    print("\n--- Excluding QH, QD, QC, QS ---")
    excluded_cards = ["QH", "QD", "QC", "QS"]
    probabilities_excluded = calculate_poker_probabilities(excluded_cards=excluded_cards)
    for hand, prob in probabilities_excluded.items():
        print(f"{hand}: {prob:.6f}%")

    # If you add four more aces
    # :kr: 에이스 네 장을 추가하는 경우
    print("\n--- Adding 4 extra Aces ---")
    added_cards = ["Extra_A1", "Extra_A2", "Extra_A3", "Extra_A4"]
    probabilities_added = calculate_poker_probabilities(added_cards=added_cards)
    for hand, prob in probabilities_added.items():
        print(f"{hand}: {prob:.6f}%")

if __name__ == "__main__":
    main()
```

## Code Result

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
