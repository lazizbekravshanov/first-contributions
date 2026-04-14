# Signing your commits

When you commit, Git records *your name and email* — but nothing stops someone else from configuring Git with your name and your email and pushing a commit that appears to be from you. Signing a commit proves that *you* (or at least, someone with access to your signing key) authored it. On GitHub, signed commits that Git recognises and verifies show up with a green **Verified** badge next to the commit.

There are two common ways to sign commits: **SSH** and **GPG**. SSH signing is newer (Git 2.34+), simpler, and lets you reuse the SSH key you already use to push to GitHub. Most first-time signers should start there.

## Signing with SSH (recommended for beginners)

If you already push to GitHub over SSH, you already have an SSH key at `~/.ssh/id_ed25519.pub` (or similar). Tell Git to use that key for signing:

```
git config --global gpg.format ssh
git config --global user.signingkey ~/.ssh/id_ed25519.pub
```

Then turn on signing by default:

```
git config --global commit.gpgsign true
```

From now on, `git commit` will sign every commit with that SSH key.

Finally, upload the same public key to GitHub **as a signing key** so it can verify your signatures. On GitHub, go to **Settings → SSH and GPG keys → New SSH key**, paste the contents of the `.pub` file, and set the **Key type** to *Signing Key*. (The same key can be registered twice — once as an Authentication key to push, once as a Signing key to verify commits.)

Make a test commit and push it. The commit page on GitHub should show a green **Verified** badge.

## Signing with GPG

If your project or employer requires GPG, the steps are similar but you'll need a GPG key first.

Generate a key:

```
gpg --full-generate-key
```

Accept the defaults (RSA, 4096 bits) and use the email address you use on GitHub. When it's done, find your key ID:

```
gpg --list-secret-keys --keyid-format=long
```

The output has a line like `sec   rsa4096/ABCD1234EFGH5678 ...`. The part after the slash (`ABCD1234EFGH5678`) is your key ID.

Configure Git to use it:

```
git config --global user.signingkey ABCD1234EFGH5678
git config --global commit.gpgsign true
```

Export your public key and add it to GitHub under **Settings → SSH and GPG keys → New GPG key**:

```
gpg --armor --export ABCD1234EFGH5678
```

Copy the output (including the `-----BEGIN PGP PUBLIC KEY BLOCK-----` and `-----END PGP PUBLIC KEY BLOCK-----` lines) into the GitHub form.

## Signing a single commit manually

If you don't want to sign *every* commit, skip the `commit.gpgsign true` step and pass `-S` when you want a specific commit signed:

```
git commit -S -m "Fix off-by-one in pagination"
```

## Checking that signing works

After committing, run:

```
git log --show-signature -1
```

You should see a line confirming the signature was made with your key. If you see `gpg: signing failed: Inappropriate ioctl for device` or a pin-entry error, export `GPG_TTY` in your shell:

```
export GPG_TTY=$(tty)
```

Add that line to your shell config (e.g. `~/.zshrc` or `~/.bashrc`) so it persists.

## A note on commit email

For GitHub's Verified badge to appear, the email on the commit must match an email you've added (and verified) on your GitHub account. If you're using GitHub's private "no-reply" email, make sure that's the one in `git config user.email`.
