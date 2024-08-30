def caesar_cipher(message, shift, mode='e'):
    result = ""
    
    # Determine the direction of the shift
    if mode == 'd':
        shift = -shift
    
    for char in message:
        # Check if character is a letter
        if char.isalpha():
            shift_base = 65 if char.isupper() else 97
            # Shift character and wrap around using modulo 26
            new_char = chr((ord(char) - shift_base + shift) % 26 + shift_base)
            result += new_char
        else:
            # If it's not a letter, leave it as it is
            result += char
    
    return result

# User input
while True:
    choice = input("Type 'e' to encrypt, 'd' to decrypt, or 'exit' to quit: ").lower()
    
    if choice == 'exit':
        print("Exiting program.")
        break
    
    if choice in ['e', 'd']:
        message = input("Enter your message: ")
        try:
            shift = int(input("Enter the shift value (0-25): "))
        except ValueError:
            print("Invalid input. Please enter an integer.")
            continue
        
        if not (0 <= shift <= 25):
            print("Shift value must be between 0 and 25.")
            continue

        result = caesar_cipher(message, shift, mode=choice)
        print(f"The {'encrypted' if choice == 'e' else 'decrypted'} message is: {result}\n")
    else:
        print("Invalid choice. Please type 'e', 'd', or 'exit'.\n")
