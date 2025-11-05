### 1. Check for existing SSH keys

Run this in your terminal:

```bash
ls -al ~/.ssh
```

Look for files like `id_rsa.pub`, `id_ed25519.pub`, or similar. If none exist, generate a new one.

---

### 2. Generate a new SSH key (recommended: Ed25519)

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

* When asked for a file path, press **Enter** to use default (`~/.ssh/id_ed25519`).
* Optionally set a passphrase (adds extra security).

---

### 3. Start the SSH agent and add the key

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

---

### 4. Copy your public key

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy the whole key that starts with `ssh-ed25519`.

---

### 5. Add key to GitLab

* Go to **GitLab → User Settings → SSH Keys**
* Paste the copied key into the box
* Set an expiration date (or leave blank for no expiry)
* Save

---

### 6. Test connection

```bash
ssh -T git@gitlab.com
```

You should see:

```
Welcome to GitLab, @your-username!
```

---

### 7. Use SSH for cloning/pushing

When cloning repos, use SSH instead of HTTPS:

```bash
git clone git@gitlab.com:username/repo.git
```
