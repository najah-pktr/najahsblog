+++
title = "Wiring Up Git and GitHub with SSH Keys: My Go-To Reference"
date = 2026-08-31
tags = ["git", "github", "ssh", "devops", "workflow"]
draft = false
+++

Let’s be honest: setting up SSH keys for Git and GitHub is one of those things you only do every once in a while, which makes it remarkably easy to forget. I built this quick guide directly into my blog so I never have to hunt around the web for the exact commands again.

Here is the exact, no-fluff workflow I use to wire up my local machine to GitHub securely via SSH.

---

## Step 1: Generate a New SSH Key

Open your terminal and run the following command to generate an Ed25519 SSH key (make sure to swap out the email with your own):

```bash
ssh-keygen -t ed25519 -C "youremail@email.com"

```

* Hit `Enter` to accept the default file location.
* Set a passphrase if you want extra security, or just press `Enter` twice to leave it empty for quick local commits.

## Step 2: Copy the Public Key String

Once the key is generated, copy the string from your public key file. You can either open the generated `.pub` file in your editor or cat it directly in the terminal to copy the contents.

Head over to your **GitHub Account Settings -> SSH and GPG keys -> New SSH key**, paste your key string in, and save it.

## Step 3: Test the Connection

To verify that everything is wired up correctly and GitHub recognizes your machine, run this command in your terminal:

```bash
ssh -T git@github.com

```

Type `yes` if a fingerprint warning pops up. If you see a success message welcoming you to GitHub, you are good to go! No more messing with personal access tokens or HTTPS credential prompts.