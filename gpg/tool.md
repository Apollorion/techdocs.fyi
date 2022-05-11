---
parent: gpg
nav_order: 3
---
# GPG Tool

I wrote a quick script to enable quickly encrypting and decrypting files and text.
You can see the source of both tools [here](https://github.com/Apollorion/techdocs.fyi/tree/main/gpg/scripts) to verify authenticity.

## Usage

Both tools require the same parameters, whether encrypting or decrypting.

| Parameter          | Optional                       | Description                                                        |
|--------------------|--------------------------------|--------------------------------------------------------------------|
| `-k` `--key`       | Required                       | The GPG Key ID to use during encryption or decryption.             |
| `-f` `--file`      | Required when `-t` is not used | The file to encrypt or decrypt.                                    |
| `-t` `--text`      | Required when `-f` is not used | The text to encrypt or decrypt.                                    |
| `-s` `--keyserver` | Optional                       | The GPG Key Server to pull the public key from if it doesnt exist. |


## Text

### Encrypting
```bash
curl -fsSL https://techdocs.fyi/gpg/scripts/encrypt | /bin/bash -s -- --key $KEYID --text "hello world"
```

### Decrypting
```bash
curl -fsSL https://techdocs.fyi/gpg/scripts/decrypt | /bin/bash -s -- --key $KEYID --file encrypted_text.gpg
```

## Files

### Encrypting
```bash
curl -fsSL https://techdocs.fyi/gpg/scripts/encrypt | /bin/bash -s -- --key $KEYID --file important_doc.csv
```

### Decrypting
Decrypting files will add `.orig` to the end of the file name, remove after decryption.
```bash
curl -fsSL https://techdocs.fyi/gpg/scripts/decrypt | /bin/bash -s -- --key $KEYID --file important_doc.csv.gpg
```

## Testing

You can test this tool using my public key, if you with (the key will automatically download from pgp.mit.edu).
```bash
curl -fsSL https://techdocs.fyi/gpg/scripts/encrypt | /bin/bash -s -- --key 2DA5A422FB5206CC9DEFC036480EA7B1693D16B8 --text "hello world"
```