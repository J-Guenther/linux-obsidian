# Setting up Git with SSH on Linux Mint

## 1. Install Git
```bash
sudo apt update
sudo apt install git
```

## 2. Configure Git identity
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

## 3. Generate an SSH key
```bash
ssh-keygen -t ed25519 -C "you@example.com"
```
- When prompted where to save, press `Enter` to accept the default location.
- You can leave the passphrase empty by pressing `Enter`, or set one for extra security.

## 4. Add SSH key to ssh-agent
Start the agent:
```bash
eval "$(ssh-agent -s)"
```
Add your SSH private key:
```bash
ssh-add ~/.ssh/id_ed25519
```

## 5. Add the SSH key to GitHub
- Display your public key:
    ```bash
    cat ~/.ssh/id_ed25519.pub
    ```
- Copy the output.
- Go to **GitHub → Settings → SSH and GPG keys → New SSH key**.
- Paste your key and save.

## 6. Test the SSH connection
```bash
ssh -T git@github.com
```
If successful, you should see:
> Hi `yourusername`! You've successfully authenticated.

---

## Notes
- When cloning repos, **use the SSH link** (`git@github.com:user/repo.git`) instead of HTTPS.
- SSH makes pushing/pulling easier without entering your username and password every time.
