# Pythonista-sm
中国国密库SM，支持sm3,sm4

# sm3
```
	y = sm3_hash(bytes_to_list(b"abc"))
	print(y)

```

# sm4
```
	key = b'KNN36H7F0MZB6RTW'
	iv = b'\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00'  # bytes类型
	crypt_sm4 = Crypt()
	# value = b'Jll9496././'  # bytes类型
	value = bytearray("test明文".encode('utf-8'))
	# 使用 CBC
	crypt_sm4.set_key(key, ENCRYPT)
	encrypt_value = crypt_sm4.crypt_cbc(iv, value)  # bytes类型
	encrypt_value = base64.b64encode(encrypt_value).decode('utf-8', 'ignore')
	print(encrypt_value.upper())  # 把所有小写字母大写

	encrypt_value = base64.b64decode(encrypt_value)
	crypt_sm4.set_key(key, DECRYPT)
	decrypt_value = crypt_sm4.crypt_cbc(iv, encrypt_value)  # bytes类型
	print(decrypt_value.decode('utf-8', 'ignore'))

	# 使用 ECB
	# crypt_sm4.set_key(key, ENCRYPT)
	# encrypt_value = crypt_sm4.crypt_ecb(value)  # bytes类型
	# print(encrypt_value)
	#
	# crypt_sm4.set_key(key, DECRYPT)
	# decrypt_value = crypt_sm4.crypt_ecb(encrypt_value)  # bytes类型
	# print(decrypt_value)


```