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

ENCRYPTION OF DES :

#include <stdio.h>
#include <string.h>
#include <stdint.h>
uint64_t stringToBinary(const char *str) {
uint64_t binary = 0;
for (int i = 0; i < 8 && str[i] != '\0'; ++i) {
binary <<= 8;
binary |= (uint64_t)str[i];
}
return binary;
}
uint32_t XOR(uint32_t a, uint32_t b) {
return a ^ b;
}

uint64_t encryptDES(uint64_t plainText) {
uint32_t left = (plainText >> 32) & 0xFFFFFFFF;
uint32_t right = plainText & 0xFFFFFFFF;
uint32_t xorResult = XOR(left, right);
uint64_t cipherText = 0;
cipherText = ((uint64_t)right << 32) | xorResult;
return cipherText;
}
int main() {
char plainText[9];
printf("\n *****DES ALGORITHM ENCRYPTION******\n\n");
printf("\n Enter an 8-character plaintext(DES): ");
fgets(plainText, sizeof(plainText), stdin);
plainText[strcspn(plainText, "\n")] = 0;
uint64_t binaryPlainText = stringToBinary(plainText);
uint64_t cipherText = encryptDES(binaryPlainText);
printf(" \n Encrypted Cipher Text in hex(DES): %016llX\n", cipherText);
return 0;
}

DECRYPTION OF DES:

#include <stdio.h>
#include <stdint.h>
#include <string.h>
// Function to convert 64-bit binary back to a string
void binaryToString(uint64_t binary, char *str) {
for (int i = 7; i >= 0; --i) {
str[i] = (char)(binary & 0xFF);
binary >>= 8;
}
str[8] = '\0'; // Null-terminate the string
}
// XOR function for 32-bit blocks
uint32_t XOR(uint32_t a, uint32_t b) {
return a ^ b;
}
// Simplified DES-like decryption (reverse of the encryption)
uint64_t decryptDES(uint64_t cipherText) {
uint32_t right = (cipherText >> 32) & 0xFFFFFFFF;
uint32_t xorResult = cipherText & 0xFFFFFFFF;
uint32_t left = XOR(right, xorResult);
uint64_t plainText = 0;
plainText = ((uint64_t)left << 32) | right;
return plainText;

}
int main() {
uint64_t cipherText;
printf("\n\n\n ****DES ALGORITHM DECRYPTION***\n\n\n");
printf(" Enter the encrypted cipher text in hex(DES): ");
scanf("%llx", &cipherText);
// Decrypt the ciphertext back to binary plaintext
uint64_t decryptedBinary = decryptDES(cipherText);
// Convert binary plaintext back to string
char decryptedText[9];
binaryToString(decryptedBinary, decryptedText);
printf("\n Decrypted Text(DES): %s\n", decryptedText);
return 0;
}
```

## OUTPUT:

ENCRYPTION (DES):

![Screenshot 2024-10-28 125324](https://github.com/user-attachments/assets/ed3a9411-f61b-476b-b1a4-3ec8a372fced)

DECRYPTION (DES):

![Screenshot 2024-10-28 125336](https://github.com/user-attachments/assets/0d4581fc-0d1f-40e5-b1ae-33f2baec2004)


## RESULT: 

Thus the program for Data Standard Encryption (DES) is executed successfully.
