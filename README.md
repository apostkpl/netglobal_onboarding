# NetGlobal Onboarding Wiki
### Instructions on how to join the Private VPN Network and gain access to our Git Server and Development Environment

***
***

## Step 0: Trust the NetGlobal Security Certificate (self-signed)

- ### How to extract the Certificate:
1. Open Google Chrome or Microsoft Edge and navigate to our management portal: `https://git.netglobal.gr`
2. You will see a "Your connection is not private" warning. 
3. Click the **"Not Secure"** warning icon located in the address bar (next to the URL).
4. Click on **"Certificate is not valid"** (or the small certificate icon).
5. A Certificate Viewer window will open. Click on the **Details** tab at the top.
6. Click the **Export** button at the bottom of the window.
7. Save the file to your computer.

**Follow the instructions for your Operating System:**

- ### Windows (10/11)

1. Double-click the downloaded `.crt` file.
2. Click **Install Certificate...**
3. Select **Local Machine** and click Next (Say "Yes" to the admin prompt).
4. Select **Place all certificates in the following store** and click **Browse**.
5. Choose **Trusted Root Certification Authorities** and click OK.
6. Click **Next**, then **Finish**. You should see a "The import was successful" message.

- ### macOS

1. Double-click the downloaded `.crt` file. This will open the **Keychain Access** app.
2. In the prompt, ensure the keychain is set to **System** and click **Add**. (Enter your Mac password if asked).
3. Find the newly imported certificate in the list (it will have a red "X" on it).
4. Double-click the certificate to open its settings.
5. Expand the **Trust** section.
6. Change the top dropdown ("When using this certificate") to **Always Trust**.
7. Close the window and enter your Mac password one more time to save. The red "X" should turn into a blue "+".

- ### Linux (Ubuntu/Debian/Fedora)
Open your terminal and run these commands to move the certificate and update the system store:
1. `sudo cp ~/Downloads/netglobal-ca.crt /usr/local/share/ca-certificates/`
2. `sudo update-ca-certificates`
3. You should see an output saying `1 added, 0 removed`.
> If your Distro isn't listed, the same instructions _should_ work. If you encounter any problems, please contact support.

***

## Step 1: VPN Access via NetBird

1. Download the **NetBird Client** for your OS: [here](https://netbird.io/downloads)
> Supports Windows, Linux, MacOS, iOS and Android
2. Install and Launch the App.
3. Right Click the tray icon -> Settings -> Advanced Settings -> Set "Management URL" to `https://git.netglobal.gr`
4. Right Click the tray icon -> Connect. If everything went well, you'll be prompted to login with your credentials.
> If you don't have any credentials yet, contact support.
5. Once Connected, the tray icon will report as such ("Netbird: Connected") and will show a green tick. You can now access our Git Instance and our Development Environment.


## Step 2: Access our repositories (self-hosted Git Server)

1. Navigate to our private [Git server](https://code.netglobal.gr).
2. Log in with your assigned credentials.
> If you don't have any credentials yet, contact support.
