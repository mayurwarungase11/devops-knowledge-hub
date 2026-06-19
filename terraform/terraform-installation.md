# Terraform Installation

## Update Packages

```bash
sudo apt update
```

## Install Required Dependencies

```bash
sudo apt install -y gnupg wget
```

## Add HashiCorp GPG Key

```bash
wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null
```

## Add HashiCorp Repository

```bash
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list
```

## Update Package Index

```bash
sudo apt update
```

## Install Terraform

```bash
sudo apt install terraform -y
```

## Verify Installation

```bash
terraform version
```
