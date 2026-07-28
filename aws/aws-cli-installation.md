# Aws Cli Installatio

Update Packages


```bash
sudo apt-get update
sudo apt-get install -y unzip curl
```
 Download AWS CLI v2

```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
```
 Unzip
```bash
unzip awscliv2.zip
```
Install
```bash
sudo ./aws/install
```
 Verify installation
```bash
aws --version
```
