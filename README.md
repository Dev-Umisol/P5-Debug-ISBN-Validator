# 📁 ISBN Validator
A Python program that validates ISBN-10 and ISBN-13 codes by recalculating and verifying their check digits.

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Project](https://img.shields.io/badge/Learning-Journey-orange)

## 📌 About
This project was built to practice reading, understanding, and debugging existing code. The program was provided with intentional errors to find and fix. It takes an ISBN code and its length as input, recalculates what the check digit should be using the official ISBN-10 and ISBN-13 algorithms, and compares it against the digit provided reporting whether the code is valid or not.

## 🧠 What I Learned
- **Reading unfamiliar code** — Working through logic I didn't write myself, understanding what each function does before attempting to debug it
- **Debugging systematically** — Identifying errors by tracing the flow of data through the program step by step rather than guessing
- `enumerate()` — Using index and value together in a loop to apply weighted multiplication across a list of digits
- **`try/except` for input validation** — Catching `ValueError` in two places: once when converting the length input to an integer, and again when an invalid character is found during ISBN validation
- **String slicing** — Splitting the ISBN into its main digits and check digit using `isbn[0:length - 1]` and `isbn[length - 1]`
- **List comprehensions** — Converting a string of digit characters into a list of integers with `[int(digit) for digit in main_digits]`
- **Modular design** — Understanding why the check digit logic is separated into `calculate_check_digit_10()` and `calculate_check_digit_13()` rather than bundled into one function

## 🛠️ Technologies Used

| Tool/Library | Purpose |
|--------------|---------|
| Python 3.x   | Core Language |
  
## 💡 How It Works

The user enters an ISBN code and its expected length (10 or 13), separated by a comma. The program then:
1. Validates that the input length matches the expected length
2. Extracts the main digits and the final check digit
3. Recalculates what the check digit should be using the official algorithm
4. Compares the two — printing `Valid ISBN Code.` or `Invalid ISBN Code.`

**ISBN-10** uses a weighted sum (multiplying digits by weights 10 down to 2), with `X` representing 10 as a valid check digit.
**ISBN-13** alternates multipliers of 1 and 3 across the first 12 digits.

**Example Usage:**
```
Enter ISBN and length: 0306406152,10
Valid ISBN Code.
```
```
Enter ISBN and length: 9780306406157,13
Valid ISBN Code.
```

## 🚀 Future Improvements

- [ ] Strip hyphens from input automatically so formats like `978-0-306-40615-7` are accepted
- [ ] Accept a file of ISBN codes and validate them all in batch
- [ ] Return a structured result (e.g. a dictionary) instead of just printing, to make the function reusable
- [ ] Write unit tests with `pytest` covering valid codes, invalid codes, wrong lengths, and edge cases like `X` check digits

## 📂 Project Structure

```
isbn-validator/
│
├── P5DebugISBNValidator.py    # Validation logic and main entry point
└── README.md
```

*Part of my Python learning journey 🐍 — practicing code reading, debugging, and understanding existing logic*
