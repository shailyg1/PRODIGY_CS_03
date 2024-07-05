import re

def check_password_strength(password):
    # Check for various criteria
    length_error = len(password) < 8
    digit_error = re.search(r"\d", password) is None
    uppercase_error = re.search(r"[A-Z]", password) is None
    lowercase_error = re.search(r"[a-z]", password) is None
    special_error = re.search(r"[ !#$%&'()*+,-./[\\\]^_`{|}~" + r'"]', password) is None

    # Dictionary to track errors for each criteria
    errors = {
        'length': length_error,
        'digit': digit_error,
        'uppercase': uppercase_error,
        'lowercase': lowercase_error,
        'special': special_error
    }

    # Strength ratings and corresponding levels
    password_strength = {
        'Very Weak': 1,
        'Weak': 2,
        'Moderate': 3,
        'Strong': 4,
        'Very Strong': 5
    }

    # Calculate the strength meter by counting the number of criteria met
    strength_meter = sum(1 for err in errors.values() if not err)

    # Determine the strength level based on the strength meter
    if strength_meter <= 2:
        strength = "Very Weak"
    elif strength_meter == 3:
        strength = "Weak"
    elif strength_meter == 4:
        strength = "Moderate"
    else:
        strength = "Strong"

    # List to store feedback/suggestions for password improvement
    feedback = []

    # Populate feedback list with specific criteria that are not met
    if length_error:
        feedback.append("- Password should be at least 8 characters long.")
    if digit_error:
        feedback.append("- Password should include at least one digit.")
    if uppercase_error:
        feedback.append("- Password should include at least one uppercase letter.")
    if lowercase_error:
        feedback.append("- Password should include at least one lowercase letter.")
    if special_error:
        feedback.append("- Password should include at least one special character (!#$%&'()*+,-./[\\\]^_`{|}~\")")

    # If password is rated as "Strong" and no specific feedback was added, provide general suggestions
    if strength == "Strong" and not feedback:
        feedback.append("- Your password meets all the criteria for a strong password. Well done!")
        feedback.append("- For future passwords, consider using a mix of random words or characters, avoiding common phrases or easily guessable information.")

    # Return strength level, rating, and feedback/suggestions
    return strength, password_strength[strength], feedback

# Function to display instructions and process user input
def password_complexity_checker():
    print("Welcome to the Password Complexity Checker!")
    print("This tool evaluates the strength of your password based on various criteria.")
    print("Criteria include:")
    print("- Minimum length of 8 characters")
    print("- Presence of at least one digit")
    print("- Presence of at least one uppercase letter")
    print("- Presence of at least one lowercase letter")
    print("- Presence of at least one special character (e.g., !#$%&'()*+,-./[\\]^_`{|}~\")")
    print()

    # Prompt user to enter password
    password = input("Enter your password: ")

    # Evaluate password strength
    strength, rating, feedback = check_password_strength(password)

    # Display results
    print(f"Your password '{password}' is {strength}. Strength rating: {rating}/5")
    
    # Display feedback/suggestions
    print("Suggestions to improve your password:")
    for suggestion in feedback:
        print(suggestion)

# Entry point of the script
if __name__ == "__main__":
    password_complexity_checker()
