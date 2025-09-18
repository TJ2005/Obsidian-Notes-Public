---
Title: Lab 8 Password Strength Calculation
Status: true
marker:
  - "[[Cybersecurity Fundamentals]]"
tags:
Date: 2025.09.16
Time: 10:09
---
# Lab 8 Password Strength Calculation

## Aim
Aim: To evaluate the strength of password-based authentication system and compare it with other authentication methods.

## Theory & Yapping
Authentication works on these principles: 
1. Something You Know: This includes passwords, PINs, or answers to security questions.
2. Something You Have: Physical devices like smart cards, security tokens, or mobile phones used in two-factor authentication (2FA).
3. Something You Are: Biometric data such as fingerprints, facial recognition, or iris scans


## Password Score Matrix & Code Explanation

I have created this matrix in the script to avoid writing a barrage if `if` and `elif` statements. 
- Get the condition to be either
	- All Upper Lower
	- Mixed
	- Mixed Numeral
	- Mixed Numeral Special
Then as per the matrix it will fall into one of these condition and give the correct output.

| Special Cases : | Blank    | All Upper Lower | Mixed    | Mixed w atleast 1 numeral | Mixed Numeral Special Character |
| --------------- | -------- | --------------- | -------- | ------------------------- | ------------------------------- |
| len < 8         | Weak     | Weak            | Moderate | Moderate                  | Moderate                        |
| 8 > len > 15    | Moderate | Moderate        | Moderate | Moderate                  | Strong                          |
| len >= 15       | Strong   | Strong          | Strong   | Strong                    | Strong                          |
### Code
```python
import sys
import string
import hashlib
from random import randint
def check_password_score(password):
    # Define the matrix
    strength_matrix = {
    "blank":      {0: "Blank"},
    "all_upper_lower": {
        "short": "Weak",
        "medium": "Moderate",
        "long": "Strong"
    },
    "mixed": {
        "short": "Moderate",
        "medium": "Moderate",
        "long": "Strong"
    },
    "mixed_numeral": {
        "short": "Moderate",
        "medium": "Moderate",
        "long": "Strong"
    },
    "mixed_numeral_special": {
        "short": "Moderate",
        "medium": "Strong",
        "long": "Strong"
    }
    }

    if len(password)<8:
        # print("Password too short, must be at least 8 characters.")
        length_category="short"
    elif 8<=len(password)<=15:
        # print("Password length is acceptable.")
        length_category="medium"
    else:
        # print("Password length is strong.")
        length_category="long"

    # print("Length category:", length_category)
    # print("Password length:", len(password))
    
    all_upper = all((c.isupper() for c in password))
    all_lower =all(c.islower()for c in password)
    all_upper_lower = all_upper or all_lower
    has_digit = any(c.isdigit() for c in password)
    has_special = any(c in string.punctuation for c in password)

    # print("all_upper_lower:", all_upper_lower)
    # print("has_digit:", has_digit)
    # print("has_special:", has_special)

    category ="mixed"
    if all_upper_lower:
        category="all_upper_lower"
    if has_digit and has_special:
        category="mixed_numeral_special"
    if has_digit and not has_special:
        category="mixed_numeral"
    print(f"Category: {category}, Length category: {length_category}")
    strength = strength_matrix[category][length_category]
    print(f"Password strength: {strength}")

    
if __name__ == "__main__":
    check_password_score(sys.argv[1])
    salt = (randint(10000000000, 99999999999))
    hashed = hashlib.sha256((sys.argv[1]+str(salt)).encode()).hexdigest()
    print("Salt:", salt)
    print("SHA-256 Hash:", hashed)
    check_password_score(hashed)
```

```bash output
PS C:\Users\tejas\prog\btech5\cybersecfundamentals> python .\file.py helooo123         
Category: mixed_numeral, Length category: medium
Password strength: Moderate
Salt: 77656664083
SHA-256 Hash: d0525870d2ed2743934a9b03364f256792d669c47e2a75ec53307e7edbad01fd
Category: mixed_numeral, Length category: long
Password strength: Strong
```

## Questions and Answers
- **Question 1** What is entropy? Explain the role of entropy in understanding the strength of password.
	- Entropy is the randomness or the measure of unpredictability in the password.
	- Entropy is a good measure to check the strength of the password.
		- Higher Entropy means $\implies$ Harder to crack and vice versa
- **Question 2** Explain the types of attacks possible on password-based authentication system.
	- **Bruteforce Attacks:** Permutating and Combinating All characters to get to the attack
		- can be a lot slower depending on the entropy
	- **Dictionary Attack:** Trying most commonly used passwords to attack vulnerable users.
	- **Keylogging:** Keyloggers can break even the most secure password systems if mfa is not present.
	- **Social Engineering:** People use their common facts as their passwords and guessing that will make them more prone to attacks.
- **Question 3:** Explain any two authentication systems other than password based.
	- **Token Based:** System generates a token for the user to use for authentication later
	- **Certificate Based:** A trust based system where third party vouches for validity 
	- **2fa:** **2FA (Two-Factor Authentication)** is a security process where users provide two different types of authentication factors to verify their identity.
- **Question 4:** 

| Method            | Security level | Usability | Cost        | Scalability | Resistance to attacks |
| ----------------- | -------------- | --------- | ----------- | ----------- | --------------------- |
| Password based    | Low-Medium     | High      | Low         | High        | Low                   |
| Token based       | High           | Medium    | Medium-High | Medium      | High                  |
| Certificate based | High           | Medium    | Medium      | High        | High                  |
| SSO               | Medium-High    | Very High | Medium      | High        | Medium-High           |
| Biometric         | High           | High      | High        | Medium      | High                  |
| 2FA               | Very High      | Medium    | Medium      | High        | Very High             |

# References


###### Information
- date: 2025.09.16
- time: 10:09