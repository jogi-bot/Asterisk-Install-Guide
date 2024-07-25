Asterisk-Install-Guide
Introduction
Welcome to the Asterisk-Install-Guide repository! This guide will walk you through the step-by-step process of installing Asterisk on an Ubuntu system. Asterisk is a powerful and flexible open-source framework for building communications applications such as IP PBX systems, VoIP gateways, and conference servers.

Table of Contents
Step 1: Update Your System
Step 2: Install Dependencies
Step 3: Download the Source Code
Step 4: Compile Asterisk
Step 5: Add the Application Macro (Optional)
Step 6: Compile Asterisk
Step 7: Test if Asterisk is Running
Step 8: Stop the Asterisk Process
Step 9: Start Asterisk in the Background
Step 10: Connect to the Asterisk Console
Conclusion
Step 1: Update Your System 🛠️
Begin by updating your package list to ensure you have the latest versions of the software:


sudo apt-get update
Step 2: Install Dependencies 📦
Asterisk requires several dependencies. Install them using the following command:


sudo apt-get install bison wget openssl libssl-dev libasound2-dev libc6-dev libxml2-dev libsqlite3-dev libnewt-dev libncurses5-dev zlib1g-dev gcc g++ make perl uuid-dev git subversion unixodbc-dev unixodbc autoconf libedit-dev
Step 3: Download the Source Code 📥
Navigate to the /usr/src directory and download the Asterisk source code:


cd /usr/src
sudo wget https://downloads.asterisk.org/pub/telephony/asterisk/old-releases/asterisk-21.0.0.tar.gz
sudo tar -xzvf asterisk-21.0.0.tar.gz
Step 4: Compile Asterisk ⚙️
Important: Since Ubuntu 18, you need to specify the complete directory name when changing directories. Replace <complete_with_the_name_where_asterisk_was_decompressed> with the actual directory name.


cd asterisk-21.0.0
sudo ./configure --with-jansson-bundled
Step 5: Add the Application Macro (Optional) 🔄
To include additional modules required by some guides, use the menuselect command to access the menu for module selection:

sudo make menuselect
In the menuselect interface, select the application macro to compile if needed. If you are going to use Asterisk 18, 19, please add the channel driver chan_sip. For Asterisk 16, it is installed by default.


Step 6: Compile Asterisk 🔧
Compile and install Asterisk using the following commands:


sudo make && sudo make install && sudo make config && sudo make samples
Step 7: Test if Asterisk is Running 🚀
To check if Asterisk is running properly, use:


sudo asterisk -vvvvvvvvgc
Step 8: Stop the Asterisk Process 🛑
To stop the Asterisk process, enter the Asterisk CLI and execute:


cli> core stop now
Step 9: Start Asterisk in the Background 🌟
To start Asterisk in the background, use:


sudo asterisk
Step 10: Connect to the Asterisk Console 🎛️
To connect to the Asterisk Console running in the background, use:

sudo asterisk -r
Conclusion 🎉
Congratulations! You’ve successfully installed Asterisk on your Ubuntu system. This guide demonstrates my dedication to simplifying complex processes and making technology accessible for everyone. Whether you’re setting up a small home system or a robust business solution, you now have the foundation to build and customize your Asterisk setup according to your needs.

Feel free to contribute to this repository by submitting issues or pull requests. Happy communicating!
