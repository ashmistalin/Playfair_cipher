# Ex.No: 02 IMPLEMENTATION OF PLAYFAIR CIPHER
### DATE: 27-02-2024                                                                          
### REGISTER NUMBER : 212221040021
### AIM: 
To implement the simple substitution technique named Plar cipher using C language.
### Steps:
1. Read the plain text from the user.
2. Read the keyword from the user.
3. Arrange the keyword without duplicates in a 5*5 matrix in the row order and fill the remaining cells with missed out letters in alphabetical order. Note that ‘i’ and ‘j’ takes the same cell.
4. Group the plain text in pairs and match the corresponding corner letters by forming a rectangular grid.
5. Display the obtained cipher text.


### Program:
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>

char ALPHABET[] = "abcdefghijklmnopqrstuvwxyz";

void encrypt(char* text, int shift) {
    for (int i = 0; text[i] != '\0'; i++) {
        if (isalpha(text[i])) {
            int index = tolower(text[i]) - 'a';
            text[i] = ALPHABET[(index + shift) % 26];
        }
    }
}

void decrypt(char* text, int shift) {
    encrypt(text, -shift);
}

int main() {
    char choice[10];
    char text[100];
    int shift;
    printf("Do you want to encrypt or decrypt? ");
    scanf("%s", choice);
    printf("Enter the text: ");
    scanf("%s", text);
    printf("Enter the shift: ");
    scanf("%d", &shift);

    if (strcmp(choice, "encrypt") == 0) {
        encrypt(text, shift);
        printf("Encrypted text: %s\n", text);
    } else if (strcmp(choice, "decrypt") == 0) {
        decrypt(text, shift);
        printf("Decrypted text: %s\n", text);
    } else {
        printf("Invalid choice.\n");
    }

    return 0;
}
```


### Output:

## Encryption:
![Screenshot (473)](https://github.com/ashmistalin/Ceaser_cipher/assets/103128410/1625b02f-588c-46e7-9073-8451412bf4fe)

## Decryption:
![Screenshot (474)](https://github.com/ashmistalin/Ceaser_cipher/assets/103128410/dc0d29b1-b4ef-4c69-9ad8-ae0210e72526)


### Result:
Thus the implementation of Playfair cipher had been executed successfully.
