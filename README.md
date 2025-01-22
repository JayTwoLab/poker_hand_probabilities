### `poker_hand_probabilities` : Poker Probability Calculator

> [English](README.md) , [Korean](README.ko.md)

This project is a Python program that calculates the probabilities of various poker hands. You can exclude or add specific cards to the standard deck and analyze how the probabilities change.

---

#### Key Features

1. **Poker Probability Calculation**  
   Calculates probabilities for the following poker hands using a standard 52-card deck:
   - `High Card`
   - `One Pair`
   - `Two Pair`
   - `Three of a Kind`
   - `Straight`
   - `Flush`
   - `Full House`
   - `Four of a Kind`
   - `Straight Flush`
   - `Royal Straight Flush`  

2. **Excluding and Adding Cards**  
   - Exclude specific cards from the deck or add new cards to recalculate probabilities.
   - Example: Exclude four Queens (Q) or add four extra Aces (A).

3. **Usage**  
   - The `calculate_poker_probabilities` function calculates probabilities considering excluded or added cards.
   - The `main` function demonstrates different scenarios (full deck, excluded cards, added cards) and prints the corresponding probabilities.

---

#### Code Example

```python
# Calculate probabilities for a full 52-card deck
probabilities = calculate_poker_probabilities()

# Exclude four Queens (Q)
excluded_cards = ["QH", "QD", "QC", "QS"]
probabilities_excluded = calculate_poker_probabilities(excluded_cards=excluded_cards)

# Add four extra Aces
added_cards = ["Extra_A1", "Extra_A2", "Extra_A3", "Extra_A4"]
probabilities_added = calculate_poker_probabilities(added_cards=added_cards)
```

---

#### How to Run

1. Ensure Python 3.x or higher is installed on your system.
2. Run the program using the following command:
   ```bash
   python poker.py
   ```
3. The program will output probabilities for each scenario.

---

#### Contribution and License

- **Contribution**: Feedback and contributions are welcome. Please submit your changes through a Pull Request.
- **License**: This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

