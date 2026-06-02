# Git Installation on Ubuntu

## Install Git

```bash
# Update package index
sudo apt update -y

# Install Git
sudo apt install git-all -y

# Verify Installation
git --version
```

## Configure Git

```bash
# Set your name
git config --global user.name "Mayur"

# Set your email
git config --global user.email "your-email@example.com"
```

## Verify Configuration

```bash
git config --list
```

## Generate SSH Key for GitHub

```bash
ssh-keygen
```

## Common Commands

```bash
git clone <repository-url>

git status

git add .

git commit -m "your message"

git push

git pull
```

## Tested On

```text
Ubuntu 24.04
AWS EC2
```
