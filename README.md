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
git clone https://github.com/covalenthq/das-ipfs-pinner
cd das-ipfs-pinner
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
docker stop light-client && docker rm light client
```
```
rm -rf das-ipfs-pinner
```
#
#
### Note: If your having this error 
"websocket: failed to close network connection: close tcp 172.17.0.3:51298->147.75.87.27:443: use of closed network connection"
#
### Update IPFS Kubo to v30 version
#
```
wget https://dist.ipfs.tech/kubo/v0.31.0/kubo_v0.31.0_linux-amd64.tar.gz
```
```
tar -xvzf kubo_v0.31.0_linux-amd64.tar.gz
```
```
cd kubo
```
```
sudo bash install.sh
```
#
### Now check 
```
ipfs --version
```
#
#
### You're good yo go now. 
