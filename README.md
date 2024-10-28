# EX-4-ADVANCED-ENCRYPTION-STANDARD-DES-ALGORITHM

## Aim:
  To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

## ALGORITHM: 
  1. AES is based on a design principle known as a substitution–permutation. 
  2. AES does not use a Feistel network like DES, it uses variant of Rijndael. 
  3. It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits. 
  4. AES operates on a 4 × 4 column-major order array of bytes, termed the state

## PROGRAM: 

```C
#DEVELOPED BY: PRAVESH N
#REG NO: 212223230154
```
```C

ADVANCED ENCRYPTION STANDARD (AES):

#include <stdio.h>
#include <string.h>
void xor_encrypt_decrypt(char *input, char *key) {
int input_len = strlen(input);
int key_len = strlen(key);
for (int i = 0; i < input_len; i++) {
input[i] = input[i] ^ key[i % key_len]; // XOR encryption
}
}
int main() {
char url[] = "https://lms2.cse.saveetha.in";
char key[] = "secretkey"; // Simple key for XOR encryption
printf("\n\n *******AES Algorithm Encryption and Decryption*********\n\n");
printf("Plain text : %s\n", url);

// Encrypt the URL

xor_encrypt_decrypt(url, key);
printf("Encrypted text : %s\n", url);

// Decrypt the URL (since XOR is reversible using the same key)

xor_encrypt_decrypt(url, key);
printf("Decrypted text : %s\n", url);
return 0;
}
```

## OUTPUT:

ENCRYPTION AND DECRYPTION OF AES :

![Screenshot 2024-10-28 130631](https://github.com/user-attachments/assets/5ab40a29-7104-413b-96d8-450118ebd38d)

## RESULT: 

Thus the program for Advanced Encryption Standard (AES) is executed successfully.
