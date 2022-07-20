# AWS CLOUD
## Server
### Configuration
| Hardware | Chunk-Only Producer Specifications |
| --- | --- |
| CPU | 4-Core  Intel(R) Xeon(R) CPU E5-2686 v4 @ 2.30GHz |
| RAM | 16G |
| Storage | 320GB SSD |

![image.png](https://cdn.nlark.com/yuque/0/2022/png/21385025/1657932770453-27e62d4c-f8c1-4c18-95c1-1167322c1aac.png#clientId=ub7ffe6d8-8a53-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=461&id=ud208fa4c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=922&originWidth=1078&originalType=binary&ratio=1&rotation=0&showTitle=false&size=169091&status=done&style=none&taskId=u872de6f4-e358-4e80-869b-11f313d06c8&title=&width=539)
### System Kernel
```bash
ubuntu@ip-172-26-8-107:~$ uname -a
Linux ip-172-26-8-107 5.15.0-1015-aws #19~20.04.1-Ubuntu SMP Wed Jun 22 19:07:51 UTC 2022 x86_64 x86_64 x86_64 GNU/Linux
```
### Price
**80usd/methons**

![image.png](https://cdn.nlark.com/yuque/0/2022/png/21385025/1657932911914-29b22cd2-0316-4734-8751-7d03c5bf8528.png#clientId=ub7ffe6d8-8a53-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=293&id=u6d31cbee&margin=%5Bobject%20Object%5D&name=image.png&originHeight=586&originWidth=1780&originalType=binary&ratio=1&rotation=0&showTitle=false&size=88483&status=done&style=none&taskId=uf9af1d47-a6d2-43ed-8e3d-f29c7f87712&title=&width=890)
## 001
This chapter is the simplest, mainly about installing node js、npm、near-cli。 Then use near cli commands
### update apt
```bash
# update apt package
sudo apt update && sudo apt upgrade -y

```
### install node & npm
```bash
curl -sL https://deb.nodesource.com/setup_18.x | sudo -E bash -  
sudo apt install build-essential nodejs
PATH="$PATH"
```
### check version
```bash
ubuntu@ip-172-26-8-107:~$ node -v
v18.6.0

ubuntu@ip-172-26-8-107:~$ npm -v
8.13.2
```
### install near-cli
```bash
# global install
sudo npm install -g near-cli
```
### command
The environment will need to be set each time a new shell is launched to select the correct network.

- GuildNet
- TestNet
- MainNet
- Shardnet (this is the network we will use for Stake Wars)
```bash
# set network tmp env
export NEAR_ENV=shardnet
```
you can also set env profile
```bash
echo 'export NEAR_ENV=shardnet' >> ~/.bashrc

# source
source ～/.bashrc
```
#### near proposals
A proposal by a validator indicates they would like to enter the validator set, in order for a proposal to be accepted it must meet the minimum seat price.
```bash
ubuntu@ip-172-26-8-107:~$ near proposals
Proposals for the epoch after next (new: 50, passing: 118, expected seat price = 530)
.--------------------------------------------------------------------------------------------------.
|       Status       |                Validator                 |   Stake => New Stake   | # Seats |
|--------------------|------------------------------------------|------------------------|---------|
| Proposal(Accepted) | benji.factory.shardnet.near              | 2,650,781 => 2,650,781 | 1       |
| Rollover           | boot2.near                               | 2,000,000              | 1       |
| Rollover           | boot1.near                               | 1,000,000              | 1       |
| Rollover           | seb.factory.shardnet.near                | 98,892                 | 1       |
| Rollover           | abahmane.factory.shardnet.near           | 85,222                 | 1       |
| Rollover           | boot4.near                               | 79,930                 | 1       |
| Rollover           | idea404.factory.shardnet.near            | 69,421                 | 1       |
| Rollover           | boot3.near                               | 16,212                 | 1       |
| Rollover           | hj-pos.factory.shardnet.near             | 15,000                 | 1       |
| Proposal(Accepted) | stakewars-de-1.factory.shardnet.near     | 10,199 => 10,199       | 1       |
| Rollover           | kiln.factory.shardnet.near               | 7,264                  | 1       |
| Proposal(Accepted) | xpool.factory.shardnet.near              | 7,030 => 7,030         | 1       |
| Proposal(Accepted) | scholtz.factory.shardnet.near            | 6,030 => 6,030         | 1       |
| Proposal(Accepted) | ou812.factory.shardnet.near              | 5,978 => 5,978         | 1       |
| Proposal(Accepted) | nodeverse.factory.shardnet.near          | 5,730                  | 1       |
| Proposal(Accepted) | idtcn0.factory.shardnet.near             | 5,530 => 5,530         | 1       |
| Proposal(Accepted) | maz0.factory.shardnet.near               | 5,030 => 5,030         | 1       |
| Rollover           | dwrx.factory.shardnet.near               | 5,003                  | 1       |
| Proposal(Accepted) | argentina-hub-pool.factory.shardnet.near | 4,830                  | 1       |
| Rollover           | 42tech.factory.shardnet.near             | 4,700                  | 1       |
| Rollover           | armada.factory.shardnet.near             | 4,530                  | 1       |
| Rollover           | beestake.factory.shardnet.near           | 4,470                  | 1       |
| Proposal(Accepted) | gigachad.factory.shardnet.near           | 4,020                  | 1       |
| Proposal(Accepted) | stakewars-de-2.factory.shardnet.near     | 3,998 => 3,998         | 1       |
| Proposal(Accepted) | alpha-centauri.factory.shardnet.near     | 3,990 => 3,990         | 1       |
| Proposal(Accepted) | vitalpointai.factory.shardnet.near       | 1,990 => 3,985         | 1       |
| Rollover           | duonghb.factory.shardnet.near            | 3,940                  | 1       |
| Rollover           | baf.factory.shardnet.near                | 3,930                  | 1       |
| Proposal(Accepted) | jiangwei.factory.shardnet.near           | 3,915 => 3,915         | 1       |
| Rollover           | imiroslav.factory.shardnet.near          | 3,820                  | 1       |
```
#### near validators current
This shows a list of active validators in the current epoch, the number of blocks produced, number of blocks expected, and online rate. Used to monitor if a validator is having issues.
```bash
ubuntu@ip-172-26-8-107:~$ near validators current
Validators (total: 107, seat price: 530):
.--------------------------------------------------------------------------------------------------------------------------------------------------.
|              Validator Id               |   Stake   | # Seats | % Online | Blocks produced | Blocks expected | Chunks produced | Chunks expected |
|-----------------------------------------|-----------|---------|----------|-----------------|-----------------|-----------------|-----------------|
| benji.factory.shardnet.near             | 2,650,781 | 1       | 99.96%   |             922 |             923 |            2133 |            2133 |
| boot2.near                              | 2,000,000 | 1       | 99.51%   |             713 |             727 |            2133 |            2133 |
| boot1.near                              | 1,000,000 | 1       | 99.91%   |             330 |             330 |            2131 |            2133 |
| seb.factory.shardnet.near               | 98,892    | 1       | 0%       |               0 |              35 |               0 |             348 |
| abahmane.factory.shardnet.near          | 85,222    | 1       | 100%     |              31 |              31 |             296 |             296 |
| boot4.near                              | 79,930    | 1       | 99.34%   |              29 |              29 |             276 |             278 |
| idea404.factory.shardnet.near           | 69,421    | 1       | 100%     |              22 |              22 |             234 |             234 |
| boot3.near                              | 16,212    | 1       | 96.29%   |               7 |               7 |              45 |              47 |
| hj-pos.factory.shardnet.near            | 15,000    | 1       | 100%     |               8 |               8 |              51 |              51 |
| stakewars-de-1.factory.shardnet.near    | 10,199    | 1       | 100%     |               1 |               1 |              54 |              54 |
| kiln.factory.shardnet.near              | 7,264     | 1       | 100%     |               2 |               2 |              39 |              39 |
| xpool.factory.shardnet.near             | 7,030     | 1       | 96.55%   |               4 |               4 |              24 |              25 |
| scholtz.factory.shardnet.near           | 6,030     | 1       | 100%     |               3 |               3 |              16 |              16 |
| ou812.factory.shardnet.near             | 5,978     | 1       | 100%     |               5 |               5 |              31 |              31 |
| idtcn0.factory.shardnet.near            | 5,530     | 1       | 100%     |               0 |               0 |              14 |              14 |
| maz0.factory.shardnet.near              | 5,030     | 1       | 100%     |               1 |               1 |              15 |              15 |
```
#### near validators next
This shows validators whose proposal was accepted one epoch ago, and that will enter the validator set in the next epoch.
```bash
ubuntu@ip-172-26-8-107:~$ near validators next

Next validators (total: 100, seat price: 530):
.-----------------------------------------------------------------------------------------.
|   Status   |                Validator                |         Stake          | # Seats |
|------------|-----------------------------------------|------------------------|---------|
| New        | june07.factory.shardnet.near            | 13,030                 | 1       |
| New        | onehis.factory.shardnet.near            | 2,010                  | 1       |
| New        | nuclear.factory.shardnet.near           | 1,998                  | 1       |
| New        | ir.factory.shardnet.near                | 1,998                  | 1       |
| New        | satman.factory.shardnet.near            | 1,930                  | 1       |
| New        | azure.factory.shardnet.near             | 1,830                  | 1       |
| New        | magicpowered.factory.shardnet.near      | 1,530                  | 1       |
| New        | macveriz.factory.shardnet.near          | 1,530                  | 1       |
| New        | withouthand.factory.shardnet.near       | 1,430                  | 1       |
| New        | ouiouane-01.factory.shardnet.near       | 1,425                  | 1       |
| New        | monish016.factory.shardnet.near         | 1,139                  | 1       |
| Rewarded   | benji.factory.shardnet.near             | 2,650,781 -> 2,650,781 | 1       |
| Rewarded   | abahmane.factory.shardnet.near          | 85,222 -> 85,222       | 1       |
| Rewarded   | stakewars-de-1.factory.shardnet.near    | 10,199 -> 10,199       | 1       |
| Rewarded   | kiln.factory.shardnet.near              | 7,264 -> 7,264         | 1       |
| Rewarded   | xpool.factory.shardnet.near             | 7,030 -> 7,030         | 1       |
| Rewarded   | scholtz.factory.shardnet.near           | 6,030 -> 6,030         | 1       |
| Rewarded   | ou812.factory.shardnet.near             | 5,978 -> 5,978         | 1       |
| Rewarded   | idtcn0.factory.shardnet.near            | 5,530 -> 5,530         | 1       |
| Rewarded   | maz0.factory.shardnet.near              | 5,030 -> 5,030         | 1       |
| Rewarded   | beestake.factory.shardnet.near          | 4,470 -> 4,470         | 1       |
| Rewarded   | stakewars-de-2.factory.shardnet.near    | 3,998 -> 3,998         | 1       |
| Rewarded   | baf.factory.shardnet.near               | 3,930 -> 3,930         | 1       |
| Rewarded   | jiangwei.factory.shardnet.near          | 3,915 -> 3,915         | 1       |
| Rewarded   | legrev.factory.shardnet.near            | 2,730 -> 3,130         | 1       |
| Rewarded   | spin.factory.shardnet.near              | 2,990 -> 2,990         | 1       |
| Rewarded   | stingray.factory.shardnet.near          | 2,495 -> 2,495         | 1       |
| Rewarded   | pero_pool.factory.shardnet.near         | 2,491 -> 2,491         | 1       |
| Rewarded   | gruberx.factory.shardnet.near           | 2,488 -> 2,488         | 1       |
| Rewarded   | zentria0.factory.shardnet.near          | 2,480 -> 2,480         | 1       |
| Rewarded   | senseinode.factory.shardnet.near        | 2,307 -> 2,307         | 1       |
| Rewarded   | do0k13.factory.shardnet.near            | 1,998 -> 1,998         | 1       |
| Rewarded   | stakefarm.factory.shardnet.near         | 1,995 -> 1,995         | 1       |
| Rewarded   | gateomega.factory.shardnet.near         | 1,995 -> 1,995         | 1       |
| Rewarded   | vitalpointai.factory.shardnet.near      | 1,990 -> 1,990         | 1       |
| Rewarded   | bondedzone.factory.shardnet.near        | 1,990 -> 1,990         | 1       |
| Rewarded   | vas.factory.shardnet.near               | 1,963 -> 1,963         | 1       |
| Rewarded   | realblocks0.factory.shardnet.near       | 1,930 -> 1,930         | 1       |
| Rewarded   | openbitlab.factory.shardnet.near        | 1,930 -> 1,930         | 1       |
| Rewarded   | alien.factory.shardnet.near             | 1,930 -> 1,930         | 1       |
| Rewarded   | marmaj.factory.shardnet.near            | 1,914 -> 1,914         | 1       |
| Rewarded   | markelov.factory.shardnet.near          | 1,830 -> 1,830         | 1       |
| Rewarded   | jagon.factory.shardnet.near             | 1,820 -> 1,820         | 1       |
| Rewarded   | ynot.factory.shardnet.near              | 1,740 -> 1,740         | 1       |
| Rewarded   | one1000lakes.factory.shardnet.near      | 1,730 -> 1,730         | 1       |
| Rewarded   | cunum.factory.shardnet.near             | 1,530 -> 1,530         | 1       |
| Rewarded   | shurik.factory.shardnet.near            | 1,530 -> 1,530         | 1       |
| Rewarded   | xrl.factory.shardnet.near               | 1,530 -> 1,530         | 1       |
| Rewarded   | leadnode.factory.shardnet.near          | 1,030 -> 1,530         | 1       |
| Rewarded   | readylayeronespac.factory.shardnet.near | 1,500 -> 1,500         | 1       |
| Rewarded   | cryptogarik.factory.shardnet.near       | 1,330 -> 1,330         | 1       |
| Rewarded   | kserx.factory.shardnet.near             | 1,330 -> 1,330         | 1       |
| Rewarded   | kalakendradao.factory.shardnet.near     | 1,031 -> 1,031         | 1       |
| Rewarded   | tamago-pool0.factory.shardnet.near      | 1,030 -> 1,030         | 1       |
| Rewarded   | dimv.factory.shardnet.near              | 1,030 -> 1,030         | 1       |
| Rewarded   | herostake.factory.shardnet.near         | 1,030 -> 1,030         | 1       |
| Rewarded   | stakin.factory.shardnet.near            | 1,030 -> 1,030         | 1       |
| Rewarded   | secdec.factory.shardnet.near            | 1,020 -> 1,020         | 1       |
| Rewarded   | max_p_node.factory.shardnet.near        | 999 -> 999             | 1       |
| Rewarded   | pool2-lovali.factory.shardnet.near      | 530 -> 530             | 1       |
| Kicked out | seb.factory.shardnet.near               | -                      | -       |
```
## 002
This challenge is focused on deploying a node (nearcore), downloading a snapshot, syncing it to the actual state of the network, then activating the node as a validator.
### Precondition
Before you start, you may want to confirm that your machine has the right CPU features.
```shell
#  install lscpu
apt install util-linux

lscpu | grep -P '(?=.*avx )(?=.*sse4.2 )(?=.*cx16 )(?=.*popcnt )' > /dev/null \
>   && echo "Supported" \
>   || echo "Not supported"
```
### Installation dependency
#### Developer tools
```bash
sudo apt install -y git binutils-dev libcurl4-openssl-dev zlib1g-dev libdw-dev build-essential make libiberty-dev cmake gcc g++ python docker.io protobuf-compiler libssl-dev pkg-config clang llvm cargo
```
#### Python pip
```bash
sudo apt install python3-pip
```
**Set the configuration**
```bash
USER_BASE_BIN=$(python3 -m site --user-base)/bin
export PATH="$USER_BASE_BIN:$PATH"
```
#### Install Rust & Cargo
> Note: if the version of rust1.59.0 is installed by default on this computer, you need to install the new version to make the environment variables take effect

```bash
ubuntu@ip-172-26-8-107:~$ /bin/rustc -V
rustc 1.59.0

```
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/21385025/1657936661024-37dbbacc-11f0-4ae0-aaf0-7dcbfe99b0b7.png#clientId=u5e0f4574-1b22-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=281&id=ueb8c1748&margin=%5Bobject%20Object%5D&name=image.png&originHeight=562&originWidth=1900&originalType=binary&ratio=1&rotation=0&showTitle=false&size=442948&status=done&style=none&taskId=ufb94620d-cc08-4db4-9aad-7f21c0a2251&title=&width=950)
please，input `y`，continue install rust
![image.png](https://cdn.nlark.com/yuque/0/2022/png/21385025/1657936772072-ca9cee19-b18c-49ee-8321-a2a4c0d960b0.png#clientId=u5e0f4574-1b22-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=505&id=u54099db4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1010&originWidth=1624&originalType=binary&ratio=1&rotation=0&showTitle=false&size=170548&status=done&style=none&taskId=ub31f560b-bfa3-4903-bde7-fad7c9df2fb&title=&width=812)
please input `1`,continue install。
```bash
source $HOME/.cargo/env
```
### Clone source code
```bash
git clone -b master https://github.com/near/nearcore
```
### Build
In the `nearcore` folder run the following commands:
```bash
cargo build -p neard --release --features shardnet
```
build will take some time. Wait a moment。finish。`neard`in `target/release`dir
```bash
ubuntu@ip-172-26-8-107:~/code/nearcore$ ls target/release/
build  deps  examples  incremental  neard  neard.d
```
### Init work dir
In order to work properly, the NEAR node requires a working directory and a couple of configuration files. Generate the initial required working directory by running:
```bash
./target/release/neard --home ~/.near init --chain-id shardnet --download-genesis
```
### update config.json
```bash
rm ~/.near/config.json
wget -O ~/.near/config.json https://s3-us-west-1.amazonaws.com/build.nearprotocol.com/nearcore-deploy/shardnet/config.json
sed -e 's/"archive": false/"archive": true/' -i config.json
```
### Get latest snapshot
**Install AWS Cli**
```bash
sudo apt-get install awscli -y
```
**Download snapshot**
```bash
cd ~/.near
# download
aws s3 --no-sign-request cp s3://build.openshards.io/stakewars/shardnet/data.tar.gz . 
# tar 
tar -xzvf data.tar.gz
# remove snapshot
rm -rf data.tar.gz
```
### Run the node
```bash
cd nearcore
./target/release/neard --home ~/.near run
```
The node is now running you can see log outputs in your console. Your node should be find peers, download headers to 100%, and then download blocks.if 100%,you can stop node。
### Activating the node as validator
**login**
```bash
near login
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/21385025/1657938045908-11505ca6-aeec-4261-8664-a3cbf2192f48.png#clientId=u9620f196-1851-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=368&id=u5a6c8855&margin=%5Bobject%20Object%5D&name=image.png&originHeight=736&originWidth=2962&originalType=binary&ratio=1&rotation=0&showTitle=false&size=124390&status=done&style=none&taskId=u1b21b204-783d-401b-82d6-3ee304431bb&title=&width=1481)
Then copy the displayed link to the browser, open it, and then log in to Shardnet wallet. If there is no account, create one,
![image.png](https://cdn.nlark.com/yuque/0/2022/png/21385025/1657938214353-b368be71-d497-4850-914a-43b23aa2ff2b.png#clientId=u9620f196-1851-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=980&id=u4a69747a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1960&originWidth=2638&originalType=binary&ratio=1&rotation=0&showTitle=false&size=244590&status=done&style=none&taskId=u77da6cbc-5942-41b4-8c29-0f92f3adf03&title=&width=1319)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/21385025/1657938252917-ecc7fb1a-1bb7-4fb9-9294-6d8259aaa8d4.png#clientId=u9620f196-1851-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=643&id=u932cbf9f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1286&originWidth=1054&originalType=binary&ratio=1&rotation=0&showTitle=false&size=103142&status=done&style=none&taskId=u743e7d3e-1ab3-4952-934d-0397cfccbda&title=&width=527)
After clicking confirm, return to the near login console interface and pause there. We need to enter the account ID, enter, and login success.
![image.png](https://cdn.nlark.com/yuque/0/2022/png/21385025/1657938410995-71fd3407-9343-4b2a-b947-999229195a53.png#clientId=u9620f196-1851-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=324&id=u44968f23&margin=%5Bobject%20Object%5D&name=image.png&originHeight=648&originWidth=2180&originalType=binary&ratio=1&rotation=0&showTitle=false&size=176367&status=done&style=none&taskId=uc396d9e5-5f23-4a73-9353-df16b7dee43&title=&width=1090)
Let's check whether the credentials exist. There should be a ${accountid} JSON file
```bash
ubuntu@ip-172-26-8-107:~/code/nearcore$ ls ~/.near-credentials/shardnet/
eth.shardnet.near.json
```
cp the credentials json file`validator_key.json`
```bash
# XXX is the file just generated after login successful
cp ~/.near-credentials/shardnet/xxx.json ~/.near/validator_key.json
```
edit`validator_key.json`

- Edit “account_id” => xx.factory.shardnet.near, where xx is your PoolName
- Change private_key to secret_key

File content must be in the following pattern:
if you accountID is `abc.shardnet.near`，the validator_key.json account_id filed is `abc.factory.shardnet.near`。
```json
{
  "account_id":"xxx.factory.shardnet.near",
  "public_key":"ed25519:Coqwefqumi1yCgAUAUfuWtzJXbHEzebS5RRPjvhqMbpV",
  "secret_key":"ed25519:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```
**start validator node**
create neard systems service
```bash
sudo vi /etc/systemd/system/neard.service
```
Paste：
```
[Unit]
Description=NEARd Daemon Service

[Service]
Type=simple
User=ubuntu
#Group=near
WorkingDirectory=/home/ubuntu/.near
ExecStart=/home/ubuntu/code/nearcore/target/release/neard run
Restart=on-failure
RestartSec=30
KillSignal=SIGINT
TimeoutStopSec=45
KillMode=mixed

[Install]
WantedBy=multi-user.target
```
>  notice：WorkingDirectory is replace your dir，ExecStart Indicates the path of your program. The code has been cloned and compiled before. It should be that path.

```bash
# Automatic startup
sudo systemctl enable neard
# start
sudo systemctl start neard
# get status
sudo systemctl status neard

# watch logs
journalctl -n 100 -f -u neard
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/21385025/1657939670432-40cf45c0-1fa1-4f3f-9a78-d48d3f04b961.png#clientId=u9620f196-1851-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=399&id=uc5af2585&margin=%5Bobject%20Object%5D&name=image.png&originHeight=798&originWidth=2922&originalType=binary&ratio=1&rotation=0&showTitle=false&size=423199&status=done&style=none&taskId=ub9c30f24-c56b-4f49-a693-2f7953e780e&title=&width=1461)
## 003
Deploy a new staking pool for your validator. Do operations on your staking pool to delegate and stake NEAR.
### create stake pool
```bash
near call factory.shardnet.near create_staking_pool '{"staking_pool_id": "<pool id>", "owner_id": "<accountId>", "stake_public_key": "<public key>", "reward_fee_fraction": {"numerator": 1, "denominator": 100}, "code_hash":"DD428g9eqLL8fWUxv8QSpVFzyHi1Qd16P8ephYCTmMSZ"}' --accountId="<accountId>" --amount=30 --gas=300000000000000
```

- pool_id：if you accountID is `abc.shardnet.near`,the `pool_id` is abc
- owner_id： you accountID is `abc.shardnet.near`,the `accountId` is `abc.shardnet.near`
- public key：field `public_key` field in `validator_key.json`
- accountId：The SHARDNET account deploying and signing the mount tx. Usually the same as the Owner ID.
- reward_fee_fraction：fee，1/100，1%

example：
```bash
near call factory.shardnet.near create_staking_pool '{"staking_pool_id": "jiangwei", "owner_id": "jiangwei.shardnet.near", "stake_public_key": "ed25519:Coqwefqumi1yCgAUAUfuWtzJXbHEzebS5RRPjvhqMbpV", "reward_fee_fraction": {"numerator": 1, "denominator": 100}, "code_hash":"DD428g9eqLL8fWUxv8QSpVFzyHi1Qd16P8ephYCTmMSZ"}' --accountId="jiangwei.shardnet.near" --amount=30 --gas=300000000000000
```
Check whether your verifier is displayed in the block browser
[**ShardNet Validator Node**](https://explorer.shardnet.near.org/nodes/validators)

![image.png](https://cdn.nlark.com/yuque/0/2022/png/21385025/1657940351275-aa6fa96c-a117-450c-9eb1-08367e5c4e4c.png#clientId=u9620f196-1851-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=563&id=u2e87f3d2&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1126&originWidth=2576&originalType=binary&ratio=1&rotation=0&showTitle=false&size=524015&status=done&style=none&taskId=uff83acf6-b9df-45c7-a229-84449c6e12f&title=&width=1288)
### Stake
use jiangwei.shardnet.near account stake 999 NEAR to jiangwei.factory.shardnet.near.
```bash
accountID=jiangwei.shardnet.near
amount=999
near call jiangwei.factory.shardnet.near  deposit_and_stake --amount $amount --accountId $accountID --gas=300000000000000
```
### Ping
A ping issues a new proposal and updates the staking balances for your delegators. A ping should be issued each epoch to keep reported rewards current
```bash
near call <staking_pool_id> ping '{}' --accountId <accountId> --gas=300000000000000
```
we can create cron job
#### near_ping.sh
```bash
ubuntu@ip-172-26-8-107:~$ cat near_ping.sh 
NEAR_ENV=shardnet near call jiangwei.factory.shardnet.near ping '{}' --accountId jiangwei.shardnet.near --gas=300000000000000
```
#### cron job
```bash
ubuntu@ip-172-26-8-107:~$ crontab -e
# auto Ping once every 5 minutes
*/5  * * * * nohup ~/near_ping.sh >> ~/near_ping.log 2>&1 &
```
## 004
Becoming a verifier is not immediately visible. After creating a take pool, the status should be proposal and being added:
![image.png](https://cdn.nlark.com/yuque/0/2022/png/21385025/1657941131656-025c4ae7-5cb6-4471-8c98-3366b4637b02.png#clientId=u9620f196-1851-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=201&id=ud8fd8b5f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=402&originWidth=2236&originalType=binary&ratio=1&rotation=0&showTitle=false&size=77978&status=done&style=none&taskId=u507786a2-1e20-4a02-a2b0-40e0d749832&title=&width=1118)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/21385025/1657940576247-8a8f4d19-44f0-4741-8548-f92d13624af8.png#clientId=u9620f196-1851-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=110&id=u592fa4c8&margin=%5Bobject%20Object%5D&name=image.png&originHeight=220&originWidth=2444&originalType=binary&ratio=1&rotation=0&showTitle=false&size=40269&status=done&style=none&taskId=uac3387d2-fd59-40da-aa64-130af7923cf&title=&width=1222)
If everything is normal, the next epoch will be effective. At present, it is about 2 hours an epoch.
if desplay Validator, it is effective
![image.png](https://cdn.nlark.com/yuque/0/2022/png/21385025/1657947816985-ae901f79-f3de-463f-943c-9b2f4bf85b36.png#clientId=uf3295f99-604a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=375&id=u89d394d8&margin=%5Bobject%20Object%5D&name=image.png&originHeight=750&originWidth=2858&originalType=binary&ratio=1&rotation=0&showTitle=false&size=440715&status=done&style=none&taskId=u3cb25bd0-054a-4205-86a6-fce2baa5eac&title=&width=1429)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/21385025/1657947222800-613c02d8-df76-42b5-90e9-e7c25e924f75.png#clientId=u9620f196-1851-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=874&id=u8aa06713&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1748&originWidth=3014&originalType=binary&ratio=1&rotation=0&showTitle=false&size=867988&status=done&style=none&taskId=uae64a93b-2434-4d61-806d-1ed10cb4867&title=&width=1507)

