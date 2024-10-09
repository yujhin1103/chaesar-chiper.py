# chaesar-chiper.py
def encrypt_caesar(plaintext, shift):
    encrypted_text = ""
    for char in plaintext:
        if char.isalpha():
            shift_base = ord('A') if char.isupper() else ord('a')
            # Menggeser huruf dengan menghitung posisi baru
            encrypted_char = chr((ord(char) - shift_base + shift) % 26 + shift_base)
            encrypted_text += encrypted_char
        else:
            # Jika bukan huruf, tambahkan karakter tanpa perubahan
            encrypted_text += char
    return encrypted_text

def decrypt_caesar(ciphertext, shift):
    decrypted_text = ""
    for char in ciphertext:
        if char.isalpha():
            shift_base = ord('A') if char.isupper() else ord('a')
            # Menggeser huruf ke posisi sebelumnya
            decrypted_char = chr((ord(char) - shift_base - shift) % 26 + shift_base)
            decrypted_text += decrypted_char
        else:
            # Jika bukan huruf, tambahkan karakter tanpa perubahan
            decrypted_text += char
    return decrypted_text

plaintext = "kriptografi!"
shift = 3

# Enkripsi
ciphertext = encrypt_caesar(plaintext, shift)
print(f"Encrypted: {ciphertext}")

# Dekripsi
decrypted_text = decrypt_caesar(ciphertext, shift)
print(f"Decrypted: {decrypted_text}")
