# Run Covalent Light Client Using Docker 
#
#
#
![GXx_B7PaUAAcyFW](https://github.com/user-attachments/assets/a12c7fc7-b00a-4904-b575-51359c334e5b)
#
## *Note: Only participants who register their burner and mainnet wallet addresses will be eligible for rewards and further participation in the testnet.*
#
### The minimum requirements for running this light node:
- CPU: 1+ cores
- RAM: 1.5 GB
- Storage: 1.5 GB
- Internet: Stable connection
#
## Let's get started!
#
```
sudo ufw enable && sudo ufw allow 22 && sudo ufw allow 433
```
#
- ### Install Docker
```
bash <(curl -s https://raw.githubusercontent.com/frianowzki/covalent-light-client/main/docker.sh)
```
#
- ### Install Go
```
bash <(curl -s https://raw.githubusercontent.com/frianowzki/covalent-light-client/main/go.sh)
```
#
- ### Install IPFS
```
bash <(curl -s https://raw.githubusercontent.com/frianowzki/covalent-light-client/main/IPFS.sh)
```
#
- ### Clone Covalent Repository
```
git clone --branch v0.11.0 --depth 1 https://github.com/covalenthq/ewm-das.git
cd ewm-das
```
#
- ### Build Image
```
docker build -t covalent/light-client -f Dockerfile.lc .
```
#
- ### Let's Run This!!!
```
docker run -d --restart always --name light-client -e PRIVATE_KEY="YOUR_HEX_PRIVATE_KEY" covalent/light-client
```
#
#### *Note: Replace "YOUR_HEX_PRIVATE_KEY" with your burner wallet private key*
#
#
#
- ### Check Logs
```
docker logs -f light-client
```
#
#
- ### ! If Only You Want To Uninstall Covalent Light Client
```
$HOME/.covalent/uninstall.sh
```
