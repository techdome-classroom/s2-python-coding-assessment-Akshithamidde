# Difficulty Level: Moderate

# Problem Statement:
def romanToInt(s: str) -> int:
    # Map of Roman numerals to integers
    roman_map = {
        'I': 1, 'V': 5, 'X': 10, 'L': 50,
        'C': 100, 'D': 500, 'M': 1000
    }
    # Initialize the total to 0
    total = 0
    # Loop through each character in the string
    for i in range(len(s)):
        # If this is not the last character and the next numeral is larger
        if i < len(s) - 1 and roman_map[s[i]] < roman_map[s[i + 1]]:
            # Subtract this numeral's value
            total -= roman_map[s[i]]
        else:
         # Add this numeral's value
            total += roman_map[s[i]]
    
    return total

# Example usage
print(romanToInt("III"))      # Output: 3
print(romanToInt("LVIII"))    # Output: 58
print(romanToInt("MCMXCIV"))  # Output: 1994
      




