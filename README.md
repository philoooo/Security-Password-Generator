<p align="center"> Password Security Hardening Generator </p>
    
<p align="center">
  <img src="https://github.com/philoooo/Security-Password-Generator/blob/main/gettyimages-1281515873-640x640.jpg" width="460" height="300" />
</p>


I imported the `random` python package. I also created a list of all letters, numbers 0-9, and symbols. Symbols can be adjusted to a system's security preferences. 
```
import random

letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']

numbers = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']

symbols = ['!', '#', '$', '%', '&', '(', ')', '*', '+']
```
Each variable accepts user input for different dimensions of the password. Depending on password length and complexity standards for the system, a user can assign any number of letters, symbols and numbers to their password.

```
print("Welcome to the Security Password Generator!")

nr_letters = int(input("How many letters would you like in your password?\n"))

nr_symbols = int(input(f"How many symbols would you like?\n"))

nr_numbers = int(input(f"How many numbers would you like?\n"))
```

Here, these for loops use the `random.choice()` function from the `random` module to randomly assign characters from the aforementioned lists of letters, symbols and numbers.

```
password_list = []

for char in range(1, nr_letters + 1):
    password_list.append(random.choice(letters))

for char in range(1, nr_symbols + 1):
    password_list.append(random.choice(symbols))

for char in range(1, nr_numbers + 1):
    password_list.append(random.choice(numbers))
```

The password is further randomized using the `random.shuffle()` function from the `random` module. This adds addition security and hardening to the password complexity, as the letters, symbols and numbers are concatenated in random order.
```

random.shuffle(password_list)

password = ""
for char in password_list:
    password += char

print(f"Your password is: {password}")
```

Here is a test case to show the user experience from my editor:

```
Welcome to the PyPassword Generator!
How many letters would you like in your password?
8
How many symbols would you like?
1
How many numbers would you like?
3
Your password is: w49ZFcASx3o*
```
