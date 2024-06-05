from collections import deque

def is_palindrome(input_string):
    # Normalize the input string: make it lower case and remove spaces
    normalized_string = ''.join(input_string.lower().split())

    # Create a two-way queue (deque) and add all characters
    char_deque = deque(normalized_string)

    while len(char_deque) > 1:
        # Compare characters at both ends
        if char_deque.popleft() != char_deque.pop():
            return False

    return True

# Test cases
test_strings = [
    "( ){[ 1 ]( 1 + 3 )( ){ }}",
    "( 23 ( 2 - 3);",
    "anna",
    "( 11 )",
    "( 11 }"
]

for test in test_strings:
    print(f"'{test}' is a palindrome: {is_palindrome(test)}")
