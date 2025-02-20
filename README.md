# Movie-Themed Coding Contest - README

## Overview
Welcome to the Movie-Themed Coding Contest! This contest consists of six coding problems, each inspired by a popular Gen Z movie or series. The problems range from easy to hard difficulty and are designed to be solved in a HackerRank-style format.

---

## Problems

### **Easy Level**

### **1. Spider-Verse Dimension Hopper**
**Theme:** *Spider-Man: Across the Spider-Verse*

#### **Problem Statement**
Miles Morales is hopping across dimensions and needs to calculate the total energy required to travel through a sequence of dimensions. Each dimension has an energy cost, and Miles can only carry a limited amount of energy at a time.

Given an array of integers representing the energy cost of each dimension and a maximum energy capacity `C`, determine the minimum number of jumps Miles needs to make to travel through all dimensions without exceeding his energy capacity.

#### **Input Format**
- First line: `N` (number of dimensions) and `C` (energy capacity)
- Second line: `N` space-separated integers representing energy costs

#### **Output Format**
- A single integer representing the minimum number of jumps

#### **Sample Input**
```
5 10
4 6 3 7 2
```

#### **Sample Output**
```
3
```

#### **Explanation**
Miles can make jumps as follows:
- **Jump 1:** Dimensions with costs `[4, 6]` (total = 10)
- **Jump 2:** Dimensions with costs `[3, 7]` (total = 10)
- **Jump 3:** Dimension with cost `[2]` (total = 2)

#### **Solution** (Python Implementation)
```python
def min_jumps(N, C, energy_costs):
    jumps = 0
    current_energy = 0
    
    for cost in energy_costs:
        if current_energy + cost > C:
            jumps += 1
            current_energy = cost
        else:
            current_energy += cost
    
    if current_energy > 0:
        jumps += 1
    
    return jumps

# Read input
N, C = map(int, input().split())
energy_costs = list(map(int, input().split()))

# Compute and print the result
print(min_jumps(N, C, energy_costs))
```

---

### **Medium Level**

### **3. Wednesday's Cryptic Message Decoder**
**Theme:** *Wednesday (Netflix Series)*

#### **Problem Statement**
Wednesday Addams finds a cryptic message in Nevermore Academy. The message is encoded using a substitution cipher where each letter is shifted by a certain number of places in the alphabet.

Given an encoded message and a shift value, decode the message back to its original form.

#### **Input Format**
- First line: `T` (number of test cases)
- Next `T` lines: Encoded message and shift value (space-separated)

#### **Output Format**
- `T` lines, each containing the decoded message

#### **Sample Input**
```
2
Khoor 3
Zrug 3
```

#### **Sample Output**
```
Hello
Word
```

#### **Explanation**
Each letter is shifted back by 3 places in the alphabet.

#### **Solution** (Python Implementation)
```python
def decode_message(encoded_message, shift):
    decoded_message = ""
    shift_amount = shift % 26
    
    for char in encoded_message:
        if char.isalpha():
            if char.islower():
                decoded_char = chr((ord(char) - ord('a') - shift_amount) % 26 + ord('a'))
            else:
                decoded_char = chr((ord(char) - ord('A') - shift_amount) % 26 + ord('A'))
            decoded_message += decoded_char
        else:
            decoded_message += char
    
    return decoded_message

# Read input
T = int(input())
for _ in range(T):
    encoded_message, shift = input().rsplit(" ", 1)
    shift = int(shift)
    print(decode_message(encoded_message, shift))
```

---

## **Contest Rules**
1. **Language:** Solutions should be written in Python.
2. **Time Limit:** Each problem has a predefined execution time limit.
3. **Correctness:** Ensure your solution handles edge cases correctly.
4. **Multiple Attempts:** Participants can attempt problems multiple times.

Good luck, and may the code be ever in your favor! 🚀🎬

