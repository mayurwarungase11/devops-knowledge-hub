⁶# Docker Installation on Ubuntu

## Step 1: Update Package Index

Update the package list to ensure the latest package information is available .

```bash
sudo apt update -y
```

## Step 2: Install Required Dependencies

Install packages required to add external repositories and download Docker packages securely.

```bash
sudo apt install -y ca-certificates curl gnupg lsb-release
```

## Step 3: Create Docker GPG Key Directory

Create a directory to store Docker's GPG key.

```bash
sudo mkdir -p /etc/apt/keyrings
```

## Step 4: Add Docker Official GPG Key

This key verifies that Docker packages come from the official Docker repository.

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

## Step 5: Add Docker Repository

Add Docker's official repository to the system.

```bash
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

## Step 6: Refresh Package Index

Fetch package information from the newly added Docker repository.

```bash
sudo apt update -y
```

## Step 7: Install Docker Engine

Install Docker Engine and related components.

```bash
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

## Step 8: Verify Installation

Check whether Docker was installed successfully.

```bash
docker --version
```

## Step 9: Start Docker Service

Start the Docker daemon.

```bash
sudo systemctl start docker
```

## Step 10: Enable Docker on Boot

Ensure Docker starts automatically after system reboot.

```bash
sudo systemctl enable docker
```

## Step 11: Check Docker Service Status

Verify that the Docker service is running.

```bash
sudo systemctl status docker
```

## Expected Output

Docker service should show:

```text
Active: active (running)
```
