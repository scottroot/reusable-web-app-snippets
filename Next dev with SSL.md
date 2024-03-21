# Proxy web app with ssl
Solves problem of `Unhandled Error: SubtleCrypto not ......` when using Web3 wallets in dev and testing on mobile or remote devices.  
### install 
```bash
npm i -g local-ssl-proxy
```
```bash
openssl req -x509 -nodes -new -sha256 -days 1024 -newkey rsa:2048 -keyout RootCA.key -out RootCA.pem -subj "/C=US/CN=Example-Root-CA"
```
```bash
openssl x509 -outform pem -in RootCA.pem -out RootCA.crt
```
### create launch script
_start-proxy.bat_ or _start-proxy.sh_  
> npx local-ssl-proxy --key RootCA.key --cert RootCA.pem --source 9000 --target 3000
