## In order to login to the NMR/ERG Remote Access Gateway you will need the following:

### The  <ins>address</ins> and ssh <ins>port</ins> of the Remote Access Gateway
This will be included in your introductory email
### Your <ins>Remote Access Password</ins>
This will be provided by a link to a one-time-use link in your introductory email
### A correctly configured Authenticator App
Configuration covered below



Please note: sensitive information such as Usernames, Passwords, Public Addresses and Hostnames are not included in this guide, and if you have questions your are advised to reply to your introductory email or contact the NMR-ERG Linux Support team at their UCL email address.

## Authenticator App
Before you are able to login, you will first need to install an authenticator app from your phone's app store and then configure it using a key you received in your introductory email.  

***DO NOT MAKE A RECORD OF THIS KEY ANYWHERE. YOU ONLY NEED TO ENTER THE KEY ONCE INTO YOUR AUTHENTICATOR APP AND THEN NEVER AGAIN.***   

You can choose one of several authenticator apps, however we recommend using either the Microsoft or Google authenticator apps.
### Microsoft Authenticator
[Android](https://play.google.com/store/apps/details?id=com.azure.authenticator&hl=en_GB) [iOS](https://apps.apple.com/us/app/microsoft-authenticator/id983156458)  
You can add your Remote Access key by clicking the + symbol in the top right corner of the application.
You will be prompted to choose "WHAT KIND OF ACCOUNT"; you should choose "Other (Google, Facebook, etc.)"  
<img src="https://github.com/NMR-ERG-Linux-Support/NMR-ERG-Remote/assets/74203354/9705e236-1956-4a79-88b0-7ffa9923f2f5" width="300" /> 
<img src="https://github.com/NMR-ERG-Linux-Support/NMR-ERG-Remote/assets/74203354/57c17546-40f7-408f-a312-1a6a6600c891" width="300" />   
**Account name** is used as a label to help identify your key when using the app, so use a clear, memorable name, such as "NMR Remote Access".
**Secret key** is a secret key provided by your introductory email. You need to enter once when you first setup the app, and then you should delete all records of it.

Once you have entered this information, you should click "Finish" at the bottom of the screen. This will complete the setup of your authenticator.


### Google Authenticator
[Android](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2&hl=en_GB) [iOS](https://apps.apple.com/us/app/google-authenticator/id388497605)  
You can add your Remote Access account by clicking the plus (+) icon at the bottom right of the app, and selecting "Enter a setup key". You will be asked for 3 things; Account name, Your key, and Type of key.

<img src="https://github.com/NMR-ERG-Linux-Support/NMR-ERG-Remote/assets/74203354/b0f47ba2-8d9e-48d9-b79a-c982ba076ba5)" width="300" /> 


**Account name** is used as a label to help identify your key when using the app, so use a clear, memorable name, such as "NMR Remote Access".
**Secret key** is a secret key provided by your introductory email. You need to enter once when you first setup the app, and then you should delete all records of it.  
**Type of key** should be set to "Time based".

Once you have entered this information, you should click "Add" at the bottom of the screen. This will complete the setup of your authenticator.

## Connecting to the Gateway
### Linux or MacOS
To login to the network from a Linux or MacOS machine, you may run the following command:

      ssh -p <ins>port</ins> username@<ins>address</ins>

replacing "username" with your Linux username, "port" with the ssh <ins>port</ins> of the server, and "gateway" with the <ins>address</ins> of the gateway (this information is included in your introductory email).

You should be asked for a password. This is where you enter your <ins>Remote Access Password</ins>.

You will then be asked for a Verification Code. This is the 6 digit code provided by the Google Authenticator app.

Once you enter the correct password and code, you will be connected to the gateway and able to then make forward connections to machines on the NMR/ERG network.

### Windows
To login to the network, you will need to install Putty. [link tbd]()  
<img src="https://github.com/NMR-ERG-Linux-Support/NMR-ERG-Remote/assets/74203354/2795d935-6fdb-4def-85d0-dc121414f592" width="300"/>

Once you have installed putty, you will need to enter the following information:  
**Host Name (or IP address)** is your username, followed by "@", followed by the gateway <ins>address</ins> provided in your email  
**Port** is the ssh <ins>port</ins> provided in your introductory email  
Note that you can save your connection settings by entering the information above, typing a configuration name under "Saved Sessions", and then clicking "Save".  


## Setting up tunnel for services, e.g. VNC Remote Desktop
Please note this is an example for demonstration purposes, and any server/workstation names used may not be valid. Please ask us if you are unsure which machine you should setup a tunnel to.
### Linux and MacOS
In order to use VNC over this connection, use the following command instead (again, replacing fields as needed. For example, replace NameOfTargetMachine with the name of a VNC host):

      ssh -p <ins>port</ins> -L 5901:<ins>NameOfTargetMachine</ins>:5956 username@<ins>address</ins>

Then, open your VNC viewer of choice and enter a host name of "localhost:5901". This will connect you to the desktop environment on whichever machine you enter as the target host.

### Windows
tbd. On the left hand menu of Putty, goto "Connection"->"SSH"->"Tunnels". You can add a local Source port along with a Destination.   
  
For example, you could enter 5901 as the Source port, and workstation:5956 as the Destination. This means if you connect a VNC client to "localhost:5901", it will instead redirect your connection to be on the "workstation"  


[These instructions are incomplete, please give any feedback you may have.]

- The NMR-ERG Linux Support team
