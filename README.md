- Copyright (c) 2009-2019 Bitcoin Developers
- Copyright (c) 2011-2019 Litecoin Developers
- Copyright (c) 2019 KhmerDigital Developers

What is KhmerDigital?
----------------

KhmerDigital is a fork of litecoin.
 - 2 minute block targets
 - 8800 KHD Block Reward till Block 1000
 - 20 KHD Block Reward till from Block 1001 to 3961000
 - 88000000 total coins
 - Explorer: http://explorer.khmerd.com

License
-------

KhmerDigital is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.


Get Started
-----------

1. For Linux: You can use both GUI and CLI version of KhmerDigital depending upon your needs.

We recommend any stable version of Ubuntu 16.04


 1.1 Installing Dependencies 

Open the terminal and run following commands one by one:


sudo apt-get install git

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev

sudo apt-get install libboost-all-dev

sudo apt-get install software-properties-common

sudo add-apt-repository ppa:bitcoin/bitcoin

sudo apt-get update

sudo apt-get install libdb4.8-dev libdb4.8++-dev

sudo apt-get install libminiupnpc-dev

sudo apt-get install libzmq3-dev

sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler 

sudo apt-get install libqt4-dev libprotobuf-dev protobuf-compiler


 1.2 Giving Permissions

Once you have installed all dependencies, next step is to give read write and execute permissions to KhmerDigitald folder. For that, go to the directory where KhmerDigitald folder is located and then do:

sudo chmod -R 777 khmerdigital/


 1.3 Compilation

After sucessfully giving all permissions, go to khmerdigital folder and run:

cd src && make clean -f makefile.unix && make -f makefile.unix

It will take a while depending upon your system's hardware configuration (RAM and Processor)


 1.4 Running khmerdigital CLI

Once compilation successfully ends, you can run khmerdigital daemon with following steps:

a) Make sure you are in src folder of khmerdigital ( your_directory/khmerdigital/src )
b) Run: ./KhmerDigitald -daemon
c) The above comamnd will create "data directory for khmerdigital"(.KhmerDigital folder) in your home folder. And will flash an error message:

(The error message flashes for the first time only, not for subsequent uses)

Error: To use the "-daemon" option, you must set a rpcpassword in the configuration file:
/home/your_linux_username/.KhmerDigital/KhmerDigital.conf
It is recommended you use the following random password:
rpcuser=KhmerDigitalrpc
rpcpassword=some_long_password
(you do not need to remember this password)
The username and password MUST NOT be the same.
If the file does not exist, create it with owner-readable-only file permissions.

d) Run: touch /home/your_linux_username/.KhmerDigital/KhmerDigitald.conf
e) Run: nano /home/your_linux_username/.KhmerDigital/KhmerDigitald.conf
NOTE: Replace "your_linux_username" in above commands with your own linux username

f) Copy rpc credentails from error message to KhmerDigital.conf file and save.
g) Run: ./KhmerDigitald -daemon ( This time there won't be any error message )
h) Run: ./KhmerDigitald getinfo (To check conenction status, blocks and other information)
You have a running CLI wallet now

i) Refer to cli-commands for more information.

 1.5 Running KhmerDigital-qt (Linux GUI Wallet)

After successfully comiling khmerdigital CLI, you can proceed for KhmerDigital-qt Wallet

a) Make sure you are in khmerdigital's root directory ( your_directory/khmerdigital)
b) Run: qmake
b) Run: make
c) You will see GUI wallet being complied on your screen, it will take some time.
d) Once compilation ends, Run: ./KhmerDigital-qt
e) You will see an KhmerDigital-qt icon in your khmerdigital's root Directory, use that for subsequent uses.

Enjoy your GUI wallet


2. For Windows: GUI client is available.

2.1 Use the setup file to install KhmerDigitald GUI Wallet

2.2 Default Location of khmerdigital's root Directory in Windows is:
    
    32-bit: Program Files/KhmerDigital
    64-bit: Program Files (x86)/KhmerDigital

2.3 Data Directory is located at: Users/your_windows_user/AppData/Roaming/KhmerDigitald


3. CLI Commands (for linux)

3.1 Make sure you are in src folder of khmerdigital ( your_directory/KhmerDigitald/src )

3.2 Run daemon: ./KhmerDigitald -daemon
    (It will take some time, press Enter key if it's too long)

3.3 Run given CLI commands to use your CLI Wallet:

a) Check you CLI Wallet's Status: ./KhmerDigitald getinfo

b) Check your Wallet's Balance: ./KhmerDigitald getbalance

c) Check number of Nodes you are connected to: ./KhmerDigitald getconnectioncount

d) Display Detailed information of Connected Nodes: ./KhmerDigitald getpeerinfo

e) Generate New Address for Wallet: ./KhmerDigitald getnewaddress

f) Send some KHD amount to an KHD address: ./KhmerDigitald sendtoaddress <KHD Address> <Amount>
   example: ./KhmerDigitald sendtoaddress Kf2kxHXm1vcZxmFdWP379zD8S7PU74owyH 10.4671

g) View all transactions in your wallet: ./KhmerDigitald listtransactions

h) Encrypt CLI and GUI Wallet: ./KhmerDigitald encryptwallet <passphrase>
   example: ./KhmerDigitald encryptwallet thehard*&password!!

i) Unlock CLI Wallet for given time (in seconds): ./KhmerDigitald walletpassphrase <passphrase> <timeout>
   example: ./KhmerDigitald walletpassphrase theahard*&password!! 90

j) Change Wallet Passphrase: ./KhmerDigitald walletpassphrasechange <oldpassphrase> <newpassphrase>
   example: ./KhmerDigitald walletpassphrase thehard*&password!! thenew%^password

