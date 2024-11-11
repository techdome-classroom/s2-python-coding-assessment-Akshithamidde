# Difficulty Level: Easy to Moderate

# Problem Statement:
def isValid(s: str) -> bool:
    # Stack to keep track of opening brackets
    stack = []
    
    # Hash map for keeping track of mappings. This provides a fast lookup of closing brackets.
    bracket_map = {")": "(", "}": "{", "]": "["}
    # Iterate over each character in the input string
    for char in s:
        # If the character is a closing bracket
        if char in bracket_map:
            # Pop the topmost element from the stack if it is non-empty, otherwise assign a dummy value
            top_element = stack.pop() if stack else '#'
            # The mapping for the closing bracket doesn't match the top element in the stack
            if bracket_map[char] != top_element:
                return False
        else:
            # It's an opening bracket, push it onto the stack
            stack.append(char)
    
    # If the stack is empty, all the brackets are matched
    return not stack
    # Example usage
print(isValid("()"))      # Output: True
print(isValid("()[]{}"))  # Output: True
print(isValid("(]"))      # Output: False
print(isValid("([)]"))    # Output: False
print(isValid("{[]}"))    # Output: True
