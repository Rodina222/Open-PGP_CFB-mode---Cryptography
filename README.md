# Open-PGP_CFB-mode-Cryptography
This code is an implementation of the PGP CFB mode encryption algorithm using the AES encryption algorithm. 

The code first imports necessary libraries including 'pycryptodome' for AES encryption and 'numpy' for array operations and then reads input files of different sizes (1KB, 5KB, 10KB, and 100KB) and splits them into 14-byte blocks. 

Then, a 32-byte key is generated using the 'os.urandom' function, and 16-byte random data is generated using 'randbytes', which is concatenated with each plaintext block. 

Next, the AES_Encrypt function takes the key and feedback register (FR) as input and encrypts the FR using the AES ECB mode to produce a modified data. The XOR function takes the plaintext and ciphertext as input and performs an element-wise XOR operation on them. The Register_update function takes the FR and ciphertext as input and updates the feedback register. 

The PGP_CFBmode function is the main function that takes plaintext, FR, and key as input and returns the ciphertext. It processes each plaintext block and encrypts it using the PGP CFB mode. The first block is handled differently, where the first 14 bytes are encrypted using the AES ECB mode and the remaining 2 bytes are encrypted separately. For all other blocks, the FR is encrypted using the AES ECB mode, and the resulting ciphertext is XORed with the plaintext to produce the cipher block. The feedback register is thenupdated using the current cipher block. The function also performs PKCS7 padding on the last block if it is shorter than 14 bytes. 

Finally, the Unpadding function is used to remove any padding characters from the last block of the ciphertext. 

Overall, this code implements the PGP CFB mode encryption algorithm using the AES encryption algorithm to encrypt input files of different sizes.
