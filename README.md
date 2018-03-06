# Salen
Shell script to install a [Salen Masternode](https://bitcointalk.org/index.php?topic=3019062.0) on a Linux server running Ubuntu 16.04. Use it on your own risk.
***

## Installation:
```
wget -q https://raw.githubusercontent.com/zoldur/Salen/master/salen_install.sh
bash salen_install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the Salen Core Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **1000** **SLN** to **MN1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6** 
* Output index:  **Second value from Step 6** It can be **0** or **1**
9. Click OK and exit the Wallet.
10. Open Salen Core Wallet, go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again.
10. Click **Start All** or **Start Alias**
11. If you are not able to see your **Masternode**, try to close and open your desktop wallet.
***

## Usage:
```
salen-cli getinfo
salen-cli masternode status
salen-cli mnsync status
```

Also, if you want to check/start/stop **Super Lumic** , run one of the following commands as **root**:

```
systemctl status Salen #To check the service is running.
systemctl start Salen #To start Salen service.
systemctl stop Salen #To stop Salen service.
systemctl is-enabled Salen #To check whetether Salen service is enabled on boot or not.
```
***

## Sentinel

**Sentinel** is installed in **/root/.salencore/sentinel/** and added to **crontab** file.  
Sentinel log file is **/root/.salencore/sentinel.log**  
Test the config by running the following commands:
```
cd /root/.salencore/sentinelsentinel
./venv/bin/py.test ./test
```
***

## Donations:  

Any donation is highly appreciated.  

**SLN**: SfhZ5hqZ4LP5pyWVsRqf29NsgUysFMEfxW  
**BTC**: 1AfsQsWfbcT2mdjRAYehuB2zegMPPG7de9  
**ETH**: 0x39d10fe57611c564abc255ffd7e984dc97e9bd6d  
**LTC**: LXrWbfeejNQRmRvtzB6Te8yns93Tu3evGf
