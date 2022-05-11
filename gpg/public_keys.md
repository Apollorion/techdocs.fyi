# Public Keys

## Downloading a Public Key
Sometimes someone may give you a public key to encrypt your data. You can download it and import it into GPG.

```bash
gpg --keyserver keys.gnupg.net --recv-keys $KEYID
```

If you were to download my public key, I would look like this:
```bash
gpg --keyserver keys.gnupg.net --recv-keys 0x480EA7B1693D16B8
```

## Uploading a Public Key

You can easily upload your public key to any key server.

```bash
gpg --keyserver pgp.mit.edu --send-key $KEYID
```
There are many key servers, some common ones are listed below:
- keys.gnupg.net
- keys.ubuntu.com
- pgp.mit.edu

After some time, the public key will propagate to other servers.