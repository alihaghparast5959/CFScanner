# CloudFlare Scanner
This script scans Millions of cloudflare IP addresses and generate a result file contains the IPs which are work with CDN

This script uses v2ray+vmess+websocket+tls by default and if you want to use it behind your Cloudflare proxy then you have to set up a vmess account, otherwise it will use the default config

## Requirements
You have to install following packages
```
git
bc
curl
nmap
parallel
```

## How to run
1. clone

```shell
[~]>$ git clone https://github.com/MortezaBashsiz/CFScanner.git
```

2. Change direcotry and make them executable

```shell
[~]>$ cd CFScanner/scripts
[~/CFScanner/scripts]> chmod +x v2ctl v2ctl-mac v2ray v2ray-mac
```

3. Get config.real

```shell
[~/CFScanner/scripts]>$ curl -s http://bot.sudoer.net/config.real -o ./config.real
```

In config file the variables are
```shell
id: UUID for user
Host: Host address which ic behind Cloudflare
Port: Port which you are using behind Cloudflare on your origin server
path: websocket endpoint like api20
serverName: SNI
```

4. Execute it

You must specify the parallel process count. In this example I execute it in 16 simultanious processes

```shell
[~/CFScanner/scripts]>$ bash cfFindIP.sh 8 ./config.real
```

5. Result
It will generate a file by datetime in result direcotry

```shell
[~/CFScanner]>$ ls result/
20230120-203358-result.cf
[~/CFScanner]>$
```
### Commands needed to work with the script
1- run scripts

1-1 cd CFScripts/scripts

1-2 ls

1-3 bash #cfFindIP.SH 16
1-4 CAT /proc/cpuinfo | grep proc
1-5 bash cfFindIP.SH 16

2- view scripts report 
2-1 cd CFScripts/result
2-2 ls -l
2-3 less (file name report)
2-4 sort -n (file name report) | less

## Video guide
A video guide usage can be found in [youtube](https://youtu.be/xzuMnxEw97U "youtube").
