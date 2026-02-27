# NetGlobal Onboarding Wiki
### Instructions on how to join the Private VPN Network and gain access to our Git Server and Development Environment

***
***
<details>
<summary><strong>Step 1: Trust the NetGlobal Security Certificate (self-signed)</strong></summary>

- ### How to extract the Certificate:
1. Open Google Chrome or Microsoft Edge and navigate to our management portal: `https://git.netglobal.gr`
2. You will see a "Your connection is not private" warning. 
3. Click the **"Not Secure"** warning icon located in the address bar (next to the URL).
4. Click on **"Certificate is not valid"**/**"Your connection to this site isn't secure"** and then on the small certificate icon.
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


</details>

***
<details>
<summary><strong>Step 2: VPN Access via NetBird</strong></summary>

- ## Instructions
1. Download the **NetBird Client** for your OS: [here](https://netbird.io/downloads)
> Supports Windows, Linux, MacOS, iOS and Android
2. Install and Launch the App.
3. Right Click the tray icon -> Settings -> Advanced Settings -> Set "Management URL" to `https://git.netglobal.gr`
4. Right Click the tray icon -> Connect. If everything went well, you'll be prompted to login with your credentials.
> If you don't have any credentials yet, contact support.
5. Once Connected, the tray icon will report as such ("Netbird: Connected") and will show a green tick. You can now access our Git Instance and our Development Environment.

</details>

***

<details>
<summary><strong>Step 3: Access our repositories (self-hosted Git Server)</strong></summary>

- ## Instructions
1. Navigate to our private Git server `https://code.netglobal.gr`.
2. Log in with your assigned credentials.
> If you don't have any credentials yet, contact support.

</details>

***

<details>
<summary><strong>Step 3a: SourceTree Users</strong></summary>

- ## Instructions
**If you prefer using a visual Git client like SourceTree instead of the command line, follow these steps to bypass the internal security certificate warnings and connect to our private Gitea server.**

### Step 1: Configure SourceTree for Internal Servers
Because our Gitea server uses an internal NetGlobal security certificate, SourceTree will block the connection by default. We need to tell it to trust our internal network.

**For Windows:**
1. Open SourceTree and go to **Tools** > **Options**.
2. Click on the **Git** tab at the top.
3. Scroll down and check the box that says **Disable SSL certificate validation**.
4. Click **OK**.

**For Mac:**
1. Open SourceTree and go to **SourceTree** > **Settings** (or Preferences).
2. Click on the **Git** tab.
3. Check the box for **Disable SSL certificate validation**.

*(Note: Since you are securely inside the NetBird VPN tunnel, disabling this specific check in SourceTree is completely safe).*

### Step 2: Clone the Repository
Now that SourceTree trusts the server, you can pull the code down.

1. Open your web browser, go to `https://code.netglobal.gr`, and log in.
2. Navigate to a repository.
3. Click the blue **Code** button to see the **Clone** options, select the **HTTPS** tab, and copy the URL provided (e.g., `https://code.netglobal.gr/NetGlobal/some_repo.git`).
4. Open SourceTree and click the **Clone / New** button (or **File >  Clone/New**).
5. In the **Source Path / URL** box, paste the link you just copied.
6. Click into the **Destination Path** box. SourceTree will briefly load and might pop up a window asking for your Gitea username and password. Enter them!
7. Choose the local folder on your computer where you want the code to live.
8. Click **Clone**.

</details>

***

<details>
<summary><strong>Step 3b: Git-CLI users</strong></summary>

## Instructions
1. Open your web browser, go to `https://code.netglobal.gr`, and log in.
2. Navigate to a repository.
3. Click the blue **Code** button to see the **Clone** options.
4. Select the **HTTPS** or **SSH** tab, and copy the URL provided (e.g., `https://code.netglobal.gr/NetGlobal/some_repo.git`, or `ssh://git@code.netglobal.gr:2222/NetGlobal/some_repo.git`).
5. **(Optional)** Recommendation: Use the SSH cloning method to be able to push locally using an SSH key, withoud the need to enter your credentials.
   - Open your Terminal (Mac/Linux) or PowerShell/Command Prompt (Windows) and paste the following command, replacing the email with your Gitea email address:
     ```
     ssh-keygen -t ed25519 -C "your.name@somemail.gr"
     ```
   - Skip the passphrase (press Enter)
   - Copy the Public Key to your clipboard:
     - For MacOS users:
       ```
       pbcopy < ~/.ssh/id_ed25519.pub
       ```
     - For Windows 10/11 users:
       ```
       type %USERPROFILE%\.ssh\id_ed25519.pub | clip
       ```
     - For Linux users:
       ```
       cat ~/.ssh/id_ed25519.pub
       ```
       
## For SSH users only (Instructions):
1. Go to `https://code.netglobal.gr` and log in.
2. Click your profile picture in the top right corner and select Settings.
3. Go to the SSH / GPG Keys tab.
4. Click the blue Add Key button.
5. Give it a name (e.g., "My Macbook Pro").
6. Paste your copied key into the Content box.
7. Click Add Key.

</details>

***
***
