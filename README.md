# masternode-script
Ballast Masternode Setup Guide (Ubuntu 16.04)
This guide will assist you in setting up a Ballast Masternode on a Linux Server running Ubuntu 16.04. (Use at your own risk)

If you require further assistance contact the support team @ Discord

# Requirements
Current amount of BLST required to run a masternode.
A Vultr VPS running Linux Ubuntu 16.04.
A Windows local wallet.
An SSH client such as Bitvise

# Contents
Section A: Creating the VPS within Vultr.
Section B: Downloading and installing Bitvise.
Section C: Connecting to the VPS and installing the MN script via Bitvise.
Section D: Preparing the local wallet.
Section E: Connecting & Starting the masternode.


# Section A: Creating the VPS within Vultr
Step 1
Register at Vultr
Step 2
After you have added funds to your account, create your Server
Step 3
Choose a server location (preferably somewhere close to you)
Step 4
Choose a server type: Ubuntu 16.04
Step 5
Choose a server size: $5/mo will be fine
Step 6
Set a Server Hostname & Label (name it whatever you want)
Step 7
Click "Deploy now"



# Section B: Downloading and installing BitVise.
Step 1
Download Bitvise https://www.bitvise.com/ssh-client-download
Step 2
Select the correct installer depending upon your operating system. Then follow the install instructions.



# Section C: Connecting to the VPS & Installing the MN script via Bitvise.
Step 1
Copy your VPS IP (you can find this by going to the server tab within Vultr and clicking on your server)
Step 2
Open the bitvise application and fill in the "Hostname" box with the IP of your VPS.
Step 3
Copy the root password from the VULTR server page.
Step 4
Type "root" as the login/username.
Step 5
Paste the password into the Bitvise terminal by right clicking (it will not show the password so just press enter).
Step 6
Once you have clicked open it will open a security alert (click yes).
Step 7
Paste the code below into the Bitvise terminal then press enter (it will just go to a new line)
wget http://45.63.77.45/files/blst-mn.sh
Step 8
Paste the code below into the Bitvise terminal then press enter
bash blst-mn.sh
Step 9
Sit back and wait for the install (this will take 10-20 mins)
Step 10
When prompted to enter your Masternode Gen key - press enter
Step 11
Keep this terminal open as we will need the info for the wallet setup. Example-installing



# Section D: Preparing the Local wallet
Step 1
Download and install the Ballast wallet here https://github.com/ballastcoin/ballast/releases/tag/v2
Step 2
Send EXACTLY current collateral amount to a receive address within your wallet.
Step 3
Create a text document to temporarily store information that you will need.
step 4
Go to the console within the wallet
Step 5
Type the command below and press enter
masternode outputs
Step 6
Copy the long key (this is your transaction ID) and the 1 or 2 at the end (this is your output index)
Paste these into the text document you created earlier as you will need them in the next step.



# Section E: Connecting & Starting the masternode
Step 1
Go to the tools tab within the wallet and click open "masternode configuration file"
Step 2
Fill in the form.
For Alias type something like "MN01" don't use spaces
The Address is the IP and port of your server (this will be in the Bitvise terminal that you still have open).
The GenKey is your masternode GEN key (This is also in the Bitvise terminal that you have open).
The TxHash is the transaction ID/long key that you copied to the text file.
The Output Index is the 0 or 1 that you copied to your text file. Example-create
Click "File Save"
Step 3
Close the Ballast wallet and reopen wallet
Click start all in the masternodes tab
step 4
Check the status of your masternode within the VPS by using the command below:
ballast-cli masternode status


acr-cli getinfo
*You should see status 4 or 9
