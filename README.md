### Python Certification Test Solutions

Welcome to my repository showcasing solutions for the HackerRank Python certification test. These solutions demonstrate my proficiency in Python programming and problem-solving skills.

**Certification:** [HackerRank Certificate]()

---

## Challenges

### 1. Vending Machine

Create a `VendingMachine` class to simulate a vending machine where users can buy items, and the machine tracks items and money transactions.

**Class: VendingMachine**

- **`__init__(self, num_items, item_price)`**
  - **Parameters:**
    - `num_items` (int): Initial number of items.
    - `item_price` (float): Price per item.
  - **Description:**
    - Initializes the vending machine with the number of items and price.

- **`buy(self, req_items, money)`**
  - **Parameters:**
    - `req_items` (int): Number of items to buy.
    - `money` (float): Amount of money inserted.
  - **Returns:**
    - Remaining change if successful.
    - `"not enough items in the machine"` if there are insufficient items.
    - `"not enough coins"` if the money is insufficient.
  - **Description:**
    - Processes the purchase of items and handles money transactions.

**Example Implementation:**

```python
class VendingMachine:
    def __init__(self, num_items, item_price):
        self.num_items = num_items
        self.item_price = item_price
    
    def buy(self, req_items, money):
        total_cost = req_items * self.item_price
        
        if req_items > self.num_items:
            return "not enough items in the machine"
        if money < total_cost:
            return "not enough coins"
        
        self.num_items -= req_items
        return round(money - total_cost, 2)
```

---

### 2. Shape Classes with Area Method

Implement two classes: `Rectangle` and `Circle`, which compute their areas.

**Rectangle Class:**

- **`__init__(self, length, width)`**
  - **Parameters:**
    - `length` (int): Length of the rectangle.
    - `width` (int): Width of the rectangle.
  - **Description:**
    - Initializes the rectangle with length and width.

- **`area(self)`**
  - **Returns:**
    - Area of the rectangle.
  - **Description:**
    - Calculates the area of the rectangle.

**Circle Class:**

- **`__init__(self, radius)`**
  - **Parameters:**
    - `radius` (int): Radius of the circle.
  - **Description:**
    - Initializes the circle with radius.

- **`area(self)`**
  - **Returns:**
    - Area of the circle using π.
  - **Description:**
    - Calculates the area of the circle.

**Implementation:**

```python
import math

class Rectangle:
    def __init__(self, length, width):
        self.length = length
        self.width = width
    
    def area(self):
        return self.length * self.width

class Circle:
    def __init__(self, radius):
        self.radius = radius
    
    def area(self):
        return math.pi * self.radius ** 2

if __name__ == "__main__":
    import sys
    input = sys.stdin.read
    data = input().split()
    
    num_queries = int(data[0])
    results = []
    
    index = 1
    for _ in range(num_queries):
        shape_type = data[index]
        if shape_type == 'rectangle':
            length = int(data[index + 1])
            width = int(data[index + 2])
            rect = Rectangle(length, width)
            results.append(f"{rect.area():.2f}")
            index += 3
        elif shape_type == 'circle':
            radius = int(data[index + 1])
            circ = Circle(radius)
            results.append(f"{circ.area():.2f}")
            index += 2
    
    for result in results:
        print(result)
```

---

### 3. String Transformation

Transform a sentence based on specific rules for each word:
- The first character remains unchanged.
- For each subsequent character, compare it to the preceding character:
  - If the preceding character comes earlier in the alphabet, transform the current character to uppercase.
  - If the current character comes earlier in the alphabet, transform it to lowercase.
  - If the characters are the same, leave the current character unchanged.

**Function Description:**

**`transformSentence(sentence: str) -> str`**

- **Parameters:**
  - `sentence` (str): The input sentence.
- **Returns:**
  - Transformed sentence as a string.

**Implementation:**

```python
import os

def transformSentence(sentence):
    # Split the sentence into words
    words = sentence.split()
    transformed_words = []
    
    # Process each word in the sentence
    for word in words:
        if not word:
            transformed_words.append('')
            continue
        
        # Start with the first character unchanged
        transformed_word = word[0]
        
        # Process the rest of the characters
        for i in range(1, len(word)):
            prev_char = word[i - 1]
            current_char = word[i]
            
            # Compare characters in a case-insensitive manner
            if prev_char.lower() < current_char.lower():
                transformed_word += current_char.upper()
            elif prev_char.lower() > current_char.lower():
                transformed_word += current_char.lower()
            else:
                transformed_word += current_char
        
        # Append the transformed word to the list
        transformed_words.append(transformed_word)
    
    # Join the transformed words with spaces and return the final sentence
    return ' '.join(transformed_words)

if __name__ == '__main__':
    # Read the input from standard input
    sentence = input().strip()  # Remove any leading/trailing whitespace
    
    # Get the transformed sentence
    result = transformSentence(sentence)
    
    # Write the result to standard output (or a file in the competition environment)
    print(result)

```

---

## Disclaimer

These solutions are personal implementations for the HackerRank Python Certification challenges. They are intended to showcase problem-solving skills and coding abilities. Please use these solutions for educational purposes and contribute your own unique solutions to the learning community.

All content related to the challenges is © HackerRank. For more challenges and to improve your coding skills, visit [HackerRank](https://www.hackerrank.com/).

## License

This project is licensed under the [MIT License](LICENSE).
