<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/764536f3-ed00-485a-aeb7-75da4ecf81ad" />## EX. NO: 1 : IMPLEMENTATION OF CAESAR CIPHER
 

## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## EXAMPLE:



![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)


## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.


PROGRAM :-
```
#include <stdio.h>
#include <string.h>

int main() {
    char text[100];
    int i, key, choice;

    printf("Enter a message: ");
    fgets(text, sizeof(text), stdin);

    // remove newline character
    text[strcspn(text, "\n")] = '\0';

    printf("Enter the key (number of shifts): ");
    scanf("%d", &key);

    printf("Choose an option:\n1. Encrypt\n2. Decrypt\nEnter choice: ");
    scanf("%d", &choice);

    for (i = 0; text[i] != '\0'; i++) {
        if (text[i] >= 'A' && text[i] <= 'Z') {   // uppercase
            if (choice == 1)  // Encryption
                text[i] = (text[i] - 'A' + key) % 26 + 'A';
            else if (choice == 2)  // Decryption
                text[i] = (text[i] - 'A' - key + 26) % 26 + 'A';
        }
        else if (text[i] >= 'a' && text[i] <= 'z') { // lowercase
            if (choice == 1)  // Encryption
                text[i] = (text[i] - 'a' + key) % 26 + 'a';
            else if (choice == 2)  // Decryption
                text[i] = (text[i] - 'a' - key + 26) % 26 + 'a';
        }
    }

    if (choice == 1)
        printf("Encrypted message: %s\n", text);
    else if (choice == 2)
        printf("Decrypted message: %s\n", text);
    else
        printf("Invalid choice!\n");

    return 0;
}

```


OUTPUT :-
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/50b8c865-fbc2-46ab-b5b9-526d489ac684" />

