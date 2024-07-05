A password strength checker evaluates the robustness of a password against common attacks and provides feedback to enhance its security. This project involves using regular expressions to check if a password meets various security criteria and gives a qualitative rating based on the results.

Core Concepts and Components
Security Criteria:

Length: Password should be at least 8 characters long.
Digits: Password should contain at least one numeric character (0-9).
Uppercase Letters: Password should contain at least one uppercase letter (A-Z).
Lowercase Letters: Password should contain at least one lowercase letter (a-z).
Special Characters: Password should contain at least one special character (e.g., !, @, #, $, etc.).
Regular Expressions (Regex):

A powerful tool for pattern matching and string manipulation. Regex is used to check for the presence of digits, uppercase letters, lowercase letters, and special characters in the password.
Strength Ratings:

Very Weak: Meets 0-2 criteria.
Weak: Meets 3 criteria.
Moderate: Meets 4 criteria.
Strong: Meets all 5 criteria.
