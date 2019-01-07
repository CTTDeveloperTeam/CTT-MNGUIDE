CryptoInvest- Taking masternodes investment game to next Level


Shell script to install a CryptoInvest Masternode on a Linux server running Ubuntu 16.04. Use it on your own risk.

VPS installation for version 1.0


wget https://github.com/CTTDeveloperTeam/CTTCoin/releases/download/v1.0/ctt-mn.sh && bash ctt-mn.sh

-------------------------------------------------------------------------------------------------------------------

Desktop wallet setup
After the Masternode is up and running, you need to configure the desktop wallet accordingly. 
Here are the steps:

Open the CryptoInvest Desktop Wallet.
Go to RECEIVE and create a New Address: MN1
Send 1000 CTT to MN1. You need to send all 1000 coins in one single transaction.
Wait for 15 confirmations.
Go to Help -> "Debug Window - Console"
Type the following command: masternode outputs
Go to Tools -> "Open Masternode Configuration File"
Add the following entry:
Alias Address Privkey TxHash TxIndex
Alias: MN1
Address: VPS_IP:PORT
Privkey: Masternode Private Key
TxHash: First value from Step 6
TxIndex: Second value from Step 6
# Example: 

MN1 127.0.0.2:57810 93HaYBVUCYjEMeeH1Y4sBGLALQZE1Yc1K64xiqgX37tGBDQL8Xg 2bcd3c84c84f87eaa86e4e56834c92927a07f9e18718810b92e0d0324456a67c 0

Save and close the file.
Go to Masternode Tab. If you tab is not shown, please enable it from: Settings - Options - Wallet - Show Masternodes Tab
Click Update status to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
Select your MN and click Start Alias to start it.
Alternatively, open Debug Console and type:

masternode start-alias mn1

Login to your VPS and check your masternode status by running the following command to confirm your MN is running:


cryptoinvest-cli masternode status

Usage:

cryptoinvest-cli masternode status
cryptoinvest-cli getinfo
cryptoinvest-cli mnsync status
