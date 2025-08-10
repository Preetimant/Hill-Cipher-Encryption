# Hill Cipher Encryption (Python, Matrix-Based)

This **Python implementation** of the Hill Cipher uses **matrix multiplication and inversion** to encrypt and decrypt ASCII-based text. It supports the english alphabet, spaces, numbers, and special characters, producing human-readable ciphertext.

---

## **Features**
- **Matrix-Based Encryption**  
  - Uses a **3×3 invertible key matrix** (determinant ≠ 0).  
  - Works on text blocks of 3 characters, mapped to ASCII values.  
  - Ciphertext mapped within **printable ASCII range (32–126)** via modular arithmetic.

- **Dynamic Key Generation**  
  - Random 3×3 key matrix generated for each session, ensuring same text produces different ciphertext in each session.
  - Ensures invertibility for successful decryption.

- **Flexible Input Handling**
  - Supports any printable characters, including spaces and symbols.  
  - Pads incomplete blocks for encryption compatibility.

- **Decryption Support**  
  - Uses inverse of the key matrix to recover plaintext.  
  - Handles rounding to counter floating-point precision issues.

---

## **Workflow**
1. **Input Processing**: Text is split into blocks of 3 characters and converted to ASCII matrices.  
2. **Encryption**: Multiply plaintext blocks by the key matrix → apply `(result % 95) + 32` → convert back to characters.  
3. **Decryption**: Multiply ciphertext by the inverse key matrix → round values → convert ASCII codes to characters.

---

## **Example**
**Plaintext**:  
```

hey Agent47, report the file to @AgentVinod

```
**Ciphertext**:  
```

zstlOp!MoYpUSrRlOp=js#3elOpF`ylOpFaYFv/lOp689lOp$Jm'@G#XaA:f

```
**Decrypted Output**:  
```

hey Agent47, report the file to @AgentVinod

````

---

## **How to Run**
1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/Hill-Cipher.git
   ````

2. Navigate to the project directory:

   ```bash
   cd Hill-Cipher
   ```
3. Run the notebook or Python script:

   ```bash
   python hill_cipher.py
   ```

   *(Or open the `.ipynb` file in Jupyter Notebook)*

---
