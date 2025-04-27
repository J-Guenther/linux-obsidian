## 1. Generate an SSH key
```bash
ssh-keygen -t ed25519 -C "you@example.com"
```
- When prompted where to save, press `Enter` to accept the default location.
- You can leave the passphrase empty by pressing `Enter`, or set one for extra security.

## 2. Add SSH key to ssh-agent
Start the agent:
```bash
eval "$(ssh-agent -s)"
```
Add your SSH private key:
```bash
ssh-add ~/.ssh/id_ed25519
```

## 3. See SSH Key
- Display your public key:
```bash
cat ~/.ssh/id_ed25519.pub
```