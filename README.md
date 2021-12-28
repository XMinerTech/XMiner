# XMiner

GPU Miner Core for `ETH`

## Disclaimer

[XMiner_github](https://github.com/XMinerTech/XMiner) are the only officially maintained site for publishing information and new releases of XMiner.

Be aware when you download XMiner binaries from other sources.

## Download

- Download all versions from [github releases](https://github.com/XMinerTech/XMiner/releases)

## Features

* Support Windows & Linux.
* Support backup mining pool configuration.
* Support SSL connection to mining pools.
* Dev Fee: 
  * ethash etchash 1%

## Requirements

- **NVIDIA Driver version: >= 384**.
- Nvidia GPU Specific Requirements:

| Algorithm        |  Coin   | Compute Capability | Memory (Win7 & Linux) | Memory (Win10) |
| :--------------- | :-----: | :----------------: | :-------------------: | :------------: |
| ethash           |   ETH   | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 |          5GB          |      6GB      |
| cuckoo_ae        |   AE    | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 |          5GB          |      6GB       |
| kawpow           |   RVN   | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 |          3GB          |      4GB      |
| beamv3 | BEAM | 6.0, 6.1, 7.0, 7.5 | 3GB | 3GB |
| octopus | CFX | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 | 5GB | 6GB |
| ergo | ERGO | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 | 3GB | 3GB |

- \* Compute Capability reference link: [wikipedia](<https://en.wikipedia.org/wiki/CUDA#GPUs_supported>)

## Sample Usages

#### ETH

- **ethermine:** XMiner -a ethash -o ethproxy+tcp://asia1.ethermine.org:4444 -u 0x12343bdgf.worker
- **f2pool:** XMiner -a ethash -o ethproxy+tcp://eth.f2pool.com:8008 -u 0x12343bdgf.worker
- **nanopool:** XMiner -a ethash -o ethproxy+tcp://eth-asia1.nanopool.org:9999 -u 0x12343bdgf.worker
- **herominers:** XMiner -a ethash -o ethproxy+tcp://ethereum.herominers.com:10201 -u 0x12343bdgf.worker
- **nicehash:** XMiner -a ethash -o nicehash+tcp://daggerhashimoto.eu.nicehash.com:3353 -u btc_address.worker
- **miningpoolhub**: XMiner -a ethash -o nicehash+tcp://asia.ethash-hub.miningpoolhub.com:20535 -u username.worker

## CMD options：

**XMiner -a algo -o protocol+socket_type://pool_host:pool_port -u wallet_address.worker -p passwd**

  * -h, --help    Displays this help.

  * -v, --version    Displays version information.

  * -a, --algo \<algo>    Select mining algorithm

  * --api  \<host:port>    The endpoint for serving REST API.

  * -o, --url \<url>    Mining pool url.

  * -u, --user \<user>    User used in Mining pool, wallet address or username.

  * -o1, --url1 \<url> url for backup mining pool 1.

  * -u1, --user1 \<user> username for backup mining pool 1.

  * -o2, --url2 \<url> url for backup mining pool 2.

* -u2, --user2 \<user> username for backup mining pool 2.

* -p,  --password \<password>  password for mining pool

* -p1,  --password1 \<password>  password for backup mining pool1

* -p2,  --password2 \<password>  password for backup mining pool2

* -d, --devices \<devices>    Specify GPU list to use. Format: "-d 0,1,2,3" to use first 4 GPU.

* --mt, --memory-tweak \<mode>    Memory timings optimize for Nvidia GDDR5 & GDDR5X gpus. range [1-6]. Higher value equals higher hashrate. Individual value can be set via comma seperated list. Power limit may need to be tuned up to get more hashrate. Higher reject share ratio can happen if mining rig hits high temperature, set lower value of `-mt` can reduce reject ratio. Under windows, a custom driver need to be installed when using `-mt`, can installed manually by option  `--driver`, or run nbminer.exe with admin privilege to perform auto-install. Under linux, admin priviledge is needed to run, `sudo ./XMiner -mt x`. `OhGodAnETHlargementPill` is not needed anymore if `-mt` is enabled when mining on 1080 & 1080ti GPUs.

* --driver \<action>    Windows only option, install / uninstall driver for `memory tweak`. Run with admin priviledge. 
  	                           install: `nbminer.exe --driver install`, uninstall: `nbminer.exe --driver uninstall`. 

* --power-limit, --pl \<limit>    Set power limit of GPU.

  ​										   Set PL in watts: -pl 200.

  ​										   Set PL in percetage of default PowerLimit: -pl 75%

* --cclock \<clocks>    Set core clock in MHz.
                                  Set clock offsets: -cclock 100, -cclock -500 (Windows only)
                                  Set locked clock: -cclock @1500.

* --mclock \<clocks>    Set memory clock offsets in MHz. (Windows only)
