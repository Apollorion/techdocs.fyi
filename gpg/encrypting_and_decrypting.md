# Encrypting and Decrypting

## Encrypting

### Encrypting a file
```bash
gpg --output ${FILENAME}.gpg --recipient $KEYID --encrypt $FILENAME
```

### Encrypting text
```bash 
echo "test message string" | gpg --encrypt --armor --recipient $KEYID -o encrypted.txt
```

## Decrypting a file
```bash
gpg --output $FILENAME --decrypt ${FILENAME}.gpg
```

## Decrypting text
```bash
gpg --decrypt --armor encrypted.txt
```