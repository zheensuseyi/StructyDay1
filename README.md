# Zheen H. Suseyi
# 10/22/2024
# StructDay1.py
print("My name is Zheen Suseyi! Here are all the functions I solved for 10/21/2024 while following the Shortly Tutorial! \n")

# PROBLEM 1
print("Write a function greet that takes in a string argument, s, and returns the string "'hey s'". No tricks here. Run the tests to check your work.")
def greet(s):
    return "hey " + s

print("***PROBLEM 1***")
print(greet("bobby"))
print("\n")
# PROBLEM 2
print("Write a function, max_value, that takes in list of numbers as an argument. The function should return the largest number in the list.")

def max_value(numbers):
    maxVal = numbers[0]
    for i in numbers:
        if i > maxVal:
            maxVal = i
    return maxVal

print("***PROBLEM 2***")
print(max_value([1, 8, 92, 5, 7]))
print("\n")

# PROBLEM 3
print("Write a function, is_prime, that takes in a number as an argument. The function should return a boolean indicating whether or not the given number is prime.")
def is_prime(n):
    if n <= 1:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

print("***PROBLEM 3***")
print(is_prime(2))  # True
print(is_prime(16))  # False
print("\n")

# PROBLEM 4
print("Write a function, anagrams, that takes in two strings as arguments. The function should return a boolean indicating whether or not the strings are anagrams. Anagrams are strings that contain the same characters, but in any order.")
def anagrams(s1, s2):
    return sorted(s1) == sorted(s2)

print("***PROBLEM 4***")
print(anagrams("hey", "yeh"))  # True
print(anagrams("MotorCycle", "MotorHome"))  # False
print("\n")

# PROBLEM 5
print("Write a function, most_frequent_char, that takes in a string as an argument. The function should return the most frequent character of the string. If there are ties, return the character that appears earlier in the string. You can assume that the input string is non-empty.")
def most_frequent_char(string):
    count = {}
    best = None
    for char in string:
        if char not in count:
            count[char] = 0
        count[char] += 1
    for char in string:
        if best is None or count[char] > count[best]:
            best = char
    return best

print("***PROBLEM 5***")
print(most_frequent_char("bookeeper"))  # 'e'
print(most_frequent_char("mississippi"))  # 'i'
print("\n")

# PROBLEM 6
print("Write a function, pair_sum, that takes in a list and a target sum as arguments. The function should return a tuple containing a pair of indices whose elements sum to the given target. The indices returned must be unique. Be sure to return the indices, not the elements themselves. There is guaranteed to be one such pair that sums to the target.")
def pair_sum(lst, target_sum):
    for i in range(len(lst)):
        for k in range(i + 1, len(lst)):
            if lst[i] + lst[k] == target_sum:
                return (i, k)

print("***PROBLEM 6***")
print(pair_sum([3, 2, 5, 4, 1], 8))  # -> (0, 2)
print(pair_sum([4, 7, 9, 2, 5, 1], 5))  # -> (0, 5)
print("\n")

# PROBLEM 7
print("Write a function, pair_product, that takes in a list and a target product as arguments. The function should return a tuple containing a pair of indices whose elements multiply to the given target. The indices returned must be unique.")
def pair_product(lst, target_product):
    for i in range(len(lst)):
        for k in range(i + 1, len(lst)):
            if lst[i] * lst[k] == target_product:
                return (i, k)

print("***PROBLEM 7***")
print(pair_product([3, 2, 5, 4, 1], 8))  # -> (1, 3)
print(pair_product([3, 2, 5, 4, 1], 10))  # -> (1, 2)
