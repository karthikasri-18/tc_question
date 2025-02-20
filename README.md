# Movie-Themed Coding Contest - README



## Easy Problem

# Harry Potter Spell Counter

## Problem Statement
Harry is practicing his spells at Hogwarts. He casts a sequence of spells, and you need to count how many times he casts his favorite spell, **"Expelliarmus"**.

## Input Format
- First line: An integer **N** representing the number of spells cast.
- Second line: **N** space-separated spell names.

## Output Format
- A single integer representing the count of "Expelliarmus" spells.

## Sample Input
```
8
Lumos Expelliarmus Alohomora Expelliarmus WingardiumLeviosa Expelliarmus Expelliarmus Accio
```

## Sample Output
```
4
```

## Explanation
The spell **"Expelliarmus"** appears **4 times** in the list.

---

## Solution (Python)
```python
# Read input
N = int(input())
spells = input().split()

# Count the occurrences of "Expelliarmus"
count = spells.count("Expelliarmus")

# Print the result
print(count)
```



### **Medium Level**

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



