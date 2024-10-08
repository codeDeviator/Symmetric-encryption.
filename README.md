# Symmetric-encryption.
Symmetric encryption and decryption using openssl commands
**OpenSSL TASK**

**Symmetric key** 

 A **symmetric key** in OpenSSL refers to a single key used for both the encryption and decryption of data in symmetric encryption algorithms like AES, DES, or ChaCha20. The key must be kept secret because anyone with access to it can decrypt the data encrypted with it.

**Characteristics of a Symmetric Key in OpenSSL**

**Same Key for Encryption and Decryption:**

In symmetric encryption, the same key is used to encrypt and decrypt the message, which differentiates it from asymmetric encryption (where different keys are used for encryption and decryption).

**Algorithms Supported:**

**AES (Advanced Encryption Standard):** A popular symmetric algorithm, often used with 128-bit, 192-bit, or 256-bit keys.  
**DES (Data Encryption Standard):** An older symmetric encryption algorithm, typically using a 56-bit key.  
**ChaCha20:** A modern stream cipher symmetric algorithm, known for efficiency and security.

**Key Length**

The key size depends on the encryption algorithm chosen. For example:

AES-128 uses a 128-bit key.  
AES-256 uses a 256-bit key.

**Generation** 

Symmetric keys can be generated using OpenSSL’s rand command, which produces cryptographically secure random numbers.

**Algorithm Used** 

**`-aes-256-cbc`** in OpenSSL refers to the **Advanced Encryption Standard (AES)** with a **256-bit key** length, using the **Cipher Block Chaining (CBC)** mode of operation.

### **Breaking it down:**

* **`aes`**: Refers to the **Advanced Encryption Standard (AES)**, which is a widely used encryption algorithm.  
* **`256`**: Indicates the **key size** in bits. In this case, it uses a 256-bit key, which provides a high level of security.  
* **`cbc`**: Stands for **Cipher Block Chaining**, which is a mode of operation for block ciphers. It adds an extra layer of security by XORing each plaintext block with the previous ciphertext block before encryption. This means that identical plaintext blocks will result in different ciphertexts, improving the overall security.

### **Encryption Algorithm:**

**AES-256-CBC (Advanced Encryption Standard with 256-bit key in Cipher Block Chaining mode)**

### **Reason for Choosing AES-256-CBC:**

1. **Strong Security**: AES is a highly secure encryption standard endorsed by the U.S. National Institute of Standards and Technology (NIST) and widely used in various industries, including government, banking, and communications.  
2. **Key Length**: AES-256 uses a 256-bit key, providing a higher level of security compared to shorter key lengths (like AES-128). It’s resistant to brute-force attacks due to the large key size.  
3. **Efficiency**: Despite its strong security, AES is computationally efficient, making it suitable for encrypting both large and small amounts of data.  
4. **CBC Mode**: The Cipher Block Chaining (CBC) mode provides an additional layer of security by ensuring that identical plaintext blocks produce different ciphertexts by XORing each plaintext block with the previous ciphertext block before encryption.

### **Key Characteristics:**

* **Key Length**: 256 bits. This long key length offers high security, protecting against brute-force attacks.  
* **Block Size**: AES operates on fixed-size blocks of 128 bits.  
* **Mode of Operation**: CBC (Cipher Block Chaining) mode, which adds complexity by chaining together the encryption of each block.  
* **Symmetric Encryption**: AES is a symmetric encryption algorithm, meaning the same key is used for both encryption and decryption.

**Steps I took :** 

1. openssl rand \-base64 256 \> key11.txt  
2. cat key11.txt  
3. echo "hey, my name is ayush and it's my encrypted file or i can call it my secret message and i will be very disappointed in me if you read it without using the key, chill i am just kidding" \>message11.txt  
4. cat message11.txt  
5. sudo openssl enc \-aes-256-cbc \-in message11.txt \-out encryptfile11.enc \-pass file:key11.txt  
6. cat encryptfile11.enc  
7. openssl enc \-aes-256-cbc \-d \-in encryptfile11.enc \-out decryptfile11.txt \-pass file:key11.txt  
8. cat decryptfile11.txt  
     
   

**Steps decoder should take to get the decrypted message :** 

1. Download the key11.txt and encryptfile11.enc files from the Google Drive folder.  
2. Then navigate to their Downloads using **cd** command and look for the file.  
3. Run the decryption command inside the Downloads Directory :   
     
   openssl enc \-aes-256-cbc \-d \-in encryptfile11.enc \-out decryptfile11.txt \-pass file:key11.txt  
4. cat decryptfile11.txt  
5. Now you will see the decrypted message.


**STEPS**

ayush@Ayush:\~$ openssl rand \-base64 256 \>key11.txt  
ayush@Ayush:\~$ cat key11.txt  
Q4uuJf6F9Xhp8CLxz1b5fykd39181yiNeA5jD6Wl/E9RwL1fK3pJ55DMHC9912m+  
9+Ia+yQMQ5pivfPd7cWXB4JOfj0IOM210qI4y9a0uBlvF/NyCPGR/fNO3DlDbMl9  
F0UeZRbERAR28ZU1vJqTWt1rmwzgNKwPxKFiES0aKarQ0galGkZxXIUgtukAVF+Y  
vcMpVPQPcrS7EG5xFp+fce1bDyrNxRGOSp8R+BnkMjpKRPK0Ko1wV279YVHvThDU  
hgxmoRzht2IvA0Rdp77sGkm710I8N6153RwhhI5rATX9gxAlBmrJyuXiddCW4pd5  
xTs91ymHMtP3nqzh7uWAxg==  
ayush@Ayush:\~$ echo "hey, my name is ayush and it's my encrypted file or i can call it my secret message and i will be very disappointed in me if you read it without using the key, chill i am just kidding" \>message11.txt  
ayush@Ayush:\~$ cat message11.txt  
hey, my name is ayush and it's my encrypted file or i can call it my secret message and i will be very disappointed in me if you read it without using the key, chill i am just kidding  
ayush@Ayush:\~$ sudo openssl enc \-aes-256-cbc \-in message11.txt \-out encryptfile11.enc \-pass file:key11.txt  
\[sudo\] password for ayush:   
\*\*\* WARNING : deprecated key derivation used.  
Using \-iter or \-pbkdf2 would be better.  
ayush@Ayush:\~$ cat encryptfile11.enc  
Salted\_\_dQ���x����C��}�P�  
6�3nP�פ���Q�\[e��U܅ƥ�${�����E�I\[��\~��▒��A��-��a�j  
                                                J�����C��Ƹu^x�.A��2sue)\[����}�\[����r�5n���0\[�z}�d(�� 02�����V�OI��O�J�t�3VD�yD�z�����@\!�:m(�����r���̷���r\\ɿ�ayush@Ayush:\~$   
ayush@Ayush:\~$ openssl enc \-aes-256-cbc \-d \-in encryptfile11.enc \-out decryptfile11.txt \-pass file:key11.txt  
\*\*\* WARNING : deprecated key derivation used.  
Using \-iter or \-pbkdf2 would be better.  
ayush@Ayush:\~$ cat decryptfile11.txt  
hey, my name is ayush and it's my encrypted file or i can call it my secret message and i will be very disappointed in me if you read it without using the key, chill i am just kidding  
ayush@Ayush:\~$ rm decryptfile11.txt  
ayush@Ayush:\~$ openssl enc \\-aes-256-cbc \\-d \\-in encryptfile11.enc \\-out decryptfile11.txt \\-pass file:key11.txt   
\*\*\* WARNING : deprecated key derivation used.  
Using \-iter or \-pbkdf2 would be better.  
ayush@Ayush:\~$ cat decryptfile11.txt  
hey, my name is ayush and it's my encrypted file or i can call it my secret message and i will be very disappointed in me if you read it without using the key, chill i am just kidding
