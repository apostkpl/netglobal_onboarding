# NetGlobal Onboarding Wiki
### Instructions on how to join the Private VPN Network and gain access to our Git Server and Development Environment

***
***

<details>
<summary><strong>Step 1: VPN Access via NetBird</strong></summary>

- ## Instructions
1. Download the **NetBird Client** for your OS: [here](https://netbird.io/downloads)
> Supports Windows, Linux, MacOS, iOS and Android
2. Install and Launch the App.
3. Right Click the tray icon -> Settings -> Advanced Settings -> Set "Management URL" to `https://vpn.netglobal.gr`
> Linux users may have to do this step via CLI, as the icon may be missing from the tray by default.
4. Right Click the tray icon -> Connect. If everything went well, you'll be prompted to login with your credentials.
> If you don't have any credentials yet, contact support.
5. Once Connected, the tray icon will report as such ("Netbird: Connected") and will show a green tick. You can now access our Git Instance and our Development Environment.

</details>

***

<details>
<summary><strong>Step 2: Access our repositories (self-hosted Git Server)</strong></summary>

- ## Instructions
1. Navigate to our private Git server `https://git.netglobal.gr`.
2. You *will* get a warning from your browser that your connection isn't secure. Ignore it, and choose to access the site. Our certificates are signed by our internal proxy server, which the Browsers don't recognize as a "Trusted Authority". The connection is indeed encrypted (https).
3. Log in with your assigned credentials.
> If you don't have any credentials yet, contact support.

</details>

***

<details>
<summary><strong>Step 2a: SourceTree Users</strong></summary>

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

1. Open your web browser, go to `https://git.netglobal.gr`, and log in.
2. Navigate to a repository.
3. Click the blue **Code** button to see the **Clone** options, select the **HTTPS** tab, and copy the URL provided (e.g., `https://git.netglobal.gr/NetGlobal/some_repo.git`).
4. Open SourceTree and click the **Clone / New** button (or **File >  Clone/New**).
5. In the **Source Path / URL** box, paste the link you just copied.
6. Click into the **Destination Path** box. SourceTree will briefly load and might pop up a window asking for your Gitea username and password. Enter them!
7. Choose the local folder on your computer where you want the code to live.
8. Click **Clone**.

</details>

***

<details>
<summary><strong>Step 2b: Git-CLI users</strong></summary>

## Instructions
1. Open your web browser, go to `https://code.netglobal.gr`, and log in.
2. Navigate to a repository.
3. Click the blue **Code** button to see the **Clone** options.
4. Select the **HTTPS** or **SSH** tab, and copy the URL provided (e.g., `https://git.netglobal.gr/NetGlobal/some_repo.git`, or `git@git.netglobal.gr:NetGlobal/some_repo.git`).
5. Paste:
   
   ```git clone https://git.netglobal.gr/NetGlobal/some_repo.git```
   
   OR
   
   ```git clone git@git.netglobal.gr:NetGlobal/some_repo.git```
   
   on your terminal.
7. **(Optional)** Recommendation: Use the SSH cloning method to be able to push locally using an SSH key, withoud the need to enter your credentials.
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
1. Go to `https://git.netglobal.gr` and log in.
2. Click your profile picture in the top right corner and select Settings.
3. Go to the SSH / GPG Keys tab.
4. Click the blue Add Key button.
5. Give it a name (e.g., "My Macbook Pro").
6. Paste your copied key into the Content box.
7. Click Add Key.

</details>

***
***
