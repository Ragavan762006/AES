# EX-8-ADVANCED-ENCRYPTION-STANDARD-DES-ALGORITHM

## Aim:
  To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

## ALGORITHM: 
  1. AES is based on a design principle known as a substitution–permutation. 
  2. AES does not use a Feistel network like DES, it uses variant of Rijndael. 
  3. It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits. 
  4. AES operates on a 4 × 4 column-major order array of bytes, termed the state

## PROGRAM: 
```

   #include <stdio.h>
#include <string.h>

void xorCrypt(char *in, char *key, char *out, int len) {
    for (int i = 0; i < len; i++) {
        out[i] = in[i] ^ key[i % strlen(key)];
    }
    out[len] = '\0';
}

int main() {
    char msg[100], key[100], enc[100], dec[100];

    printf("Enter message: ");
    fgets(msg, 100, stdin);
    msg[strcspn(msg, "\n")] = 0;

    printf("Enter key: ");
    fgets(key, 100, stdin);
    key[strcspn(key, "\n")] = 0;

    int len = strlen(msg);

    // Encrypt
    xorCrypt(msg, key, enc, len);
    printf("Encrypted: ");
    for (int i = 0; i < len; i++) {
        printf("%02X ", (unsigned char)enc[i]);
    }
    printf("\n");

    // Decrypt
    xorCrypt(enc, key, dec, len);
    printf("Decrypted: %s\n", dec);

    return 0;
}
 
```
## OUTPUT:
<img width="947" height="383" alt="image" src="https://github.com/user-attachments/assets/18af7b6e-7869-4a43-abc2-d1c58dae7a7d" />


## RESULT: 
 Hence,to use Advanced Encryption Standard (AES) Algorithm for a practical
 application like URL Encryption is done successfully.
