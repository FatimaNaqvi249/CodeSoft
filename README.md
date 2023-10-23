# CodeSoft
#Task1 "Password Generator"
import random
import string
def generate_password(length):
    lowercase = string.ascii_lowercase
    uppercase = string.ascii_uppercase
    digits = string.digits
    special_chars = string.punctuation
    
    complexity = input("Enter password complexity (L for Low, M for Medium, H for High): ")
    if complexity.lower() == 'l':
        characters = lowercase + digits
    elif complexity.lower() == 'm':
        characters = lowercase + uppercase + digits
    elif complexity.lower() == 'h':
        characters = lowercase + uppercase + digits + special_chars
    else:
        print("Error! Invalid complexity choice.")
        return None
    password = ''.join(random.choice(characters) for _ in range(length))
    return password

def main():
    print("\n\t----------Welcome to the Password Generator Application----------")
    try:           
        password_length = int(input("\nPlease specify the desired length of the password: "))
        if password_length <= 0:
            print("Invalid input. Try again!")
            return
        generated_password = generate_password(password_length)
        print("\n\tYour Generated Password is: ", generated_password)
        print("\n\t\t\tThank You!")
    except ValueError:
        print("Invalid input. Please enter a valid positive integer.")
if __name__ == "__main__":
    main()
    
    
    
