# Install SideStore on iPhone from Windows

You need a Windows PC, a USB data cable, an iPhone with a passcode, Wi-Fi, and a free Apple Account. Use your own Apple Account in iLoader and SideStore. The PC and cable are for the initial install and for repairing pairing if needed.

> **Turn on LocalDevVPN and connect to Wi-Fi before every step inside SideStore.** Keep both connected while changing SideStore settings, signing in, adding the source, installing or updating apps, and refreshing signatures.

## 1. Enable Developer Mode on the iPhone

1. On the iPhone, open **Settings → Privacy & Security → Developer Mode**.
2. Turn on **Developer Mode** and tap **Restart**. After the restart, unlock the phone, tap **Turn On**, and enter the passcode.
3. If **Developer Mode** is missing, finish steps 2 and 3 below, then return here. The setting may appear only after pairing or after installing SideStore. Developer Mode applies on iOS 16 and later. [Apple’s Developer Mode guide](https://developer.apple.com/documentation/xcode/enabling-developer-mode-on-a-device)

## 2. Install Apple Devices on Windows

1. Open Microsoft Store and install **Apple Devices** by Apple Inc. [Apple Devices download](https://apps.microsoft.com/detail/9np83lwlpz9k)
2. Connect the unlocked iPhone by USB. Open **Apple Devices**, select the phone in the sidebar, and accept any **Trust** prompt on the PC or iPhone. Enter the iPhone passcode if requested.
3. Confirm the phone appears in Apple Devices. If it does not, unlock it, reconnect with a data cable, or try another USB port. If Apple Devices sees it but iLoader still cannot, try the Apple iTunes driver setup in the [SideStore Windows prerequisites](https://docs.sidestore.io/docs/installation/prerequisites).

## 3. Install the latest SideStore with iLoader

1. Open the latest **iLoader** release on the Windows PC. Under **Assets**, download and run the Windows MSI for your PC. Most PCs use `iloader-windows-x64.msi`. [iLoader releases](https://github.com/nab138/iloader/releases/latest)
2. Keep the iPhone connected and unlocked. Open iLoader, select the iPhone, and sign in with your free Apple Account. Enter Apple's verification code if prompted.
3. Use **Install SideStore (Stable)** if it offers a current build. If that button offers **0.6.4 or older**, or if you want to select the exact latest published build, download **SideStore.ipa** under **Assets** on the official release page. Use iLoader’s **Install IPA** option to select that file. The latest published release when this guide was checked was **0.7.0-alpha**. SideStore’s release notes flag sign-in problems on 0.6.4 and earlier. [SideStore releases](https://github.com/SideStore/SideStore/releases/latest) · [iLoader setup guide](https://docs.sidestore.io/docs/installation/install)
4. Once the icon appears, go to **iPhone Settings → General → VPN & Device Management → Developer App → your Apple Account → Trust**. If you see **Allow & Restart**, tap it and follow the prompts. If Developer Mode was missing earlier, turn it on now using step 1.
5. Complete step 5 below before opening SideStore. iLoader normally places the pairing file during setup.

## 4. Repair or import the pairing file only if needed

Skip this section if SideStore opens without a pairing prompt and can refresh. Pairing files are specific to each iPhone. Keep the file private. An iOS update or reset can require a new one.

**Try iLoader first.** Connect the unlocked iPhone. In iLoader select the phone, choose **Delete Stored Pairing**, then select it again and accept **Trust** on the phone. Open **Manage Pairing File** and tap **Place** beside **SideStore**. [SideStore pairing repair guide](https://docs.sidestore.io/docs/advanced/pairing-file)

**If you need a file manually, use idevice_pair.**

1. On the Windows PC, download the Windows executable under **Assets** and open it. Keep the iPhone plugged in and unlocked. [idevice_pair releases](https://github.com/jkcoxson/idevice_pair/releases/latest)
2. Select the iPhone in idevice_pair. Under **Pairing file**, select **Lockdown**, then click **Create** or **Load**, whichever appears. Accept **Trust** on the iPhone if asked.
3. Under **Send to an app**, click **SideStore** and wait for **Sent**. If you need to pick a file yourself, use **Save to file…** and keep the generated `.mobiledevicepairing` or `.plist` extension. Move the file privately into the iPhone’s **Files** app, for example using your own iCloud Drive.
4. Connect **LocalDevVPN** and Wi-Fi. If SideStore asks for a pairing file when it opens, select your file in **Files**. To replace one from inside SideStore, go to **Settings → Advanced Settings → Reset Pairing File** and follow the file picker prompt. [idevice_pair controls](https://github.com/jkcoxson/idevice_pair/blob/v1.2.0/src/ui/device_page.rs) · [SideStore pairing file formats](https://github.com/SideStore/SideStore/blob/0.7.0-alpha/SideStore/Core/Pairing/PairingFileManager.swift)

## 5. Install and connect LocalDevVPN

1. On the iPhone, install **LocalDevVPN** from the App Store. [LocalDevVPN download](https://apps.apple.com/app/localdevvpn/id6755608044)
2. Connect the iPhone to **Wi-Fi**. Open **LocalDevVPN → Connect**. If iOS asks to add a VPN configuration, tap **Allow** and enter the passcode.
3. Confirm LocalDevVPN shows **Connected**. Keep it connected for every step inside SideStore, including the settings and source steps below. The PC can be disconnected once SideStore and its pairing file are installed. [SideStore network requirements](https://docs.sidestore.io/docs/installation/prerequisites)

## 6. Apply the SideStore settings and sign in

These settings use the values supplied in `SideStoreConfig.txt`. Apply them inside **SideStore** while **LocalDevVPN and Wi-Fi** are connected.

1. Tap **SideStore → Settings** (gear icon) → **Advanced Settings → User Customizations**. In the **Anisette** section, turn **On-Device Anisette** **off**. Reopen SideStore if it asks you to restart. Check LocalDevVPN is still connected.
2. Go back to the main **SideStore → Settings** screen and open **Anisette Servers**. Tap **jkcoxson** to select it. Scroll to the bottom of the same screen and turn **Enable Auto Rotation** **off**.
3. Go to **SideStore → Settings → Advanced Settings → User Customizations → Anisette Client Configuration**. Replace the text in **Client Info** with this single line:

   ```text
   <MacBookPro13,3> <Mac OS X;26.6;25F84> <com.apple.AuthKit/1 (com.apple.akd/1.0)>
   ```

4. On the same screen, replace **User Agent** with this single line:

   ```text
   akd/1.0 CFNetwork/811.5.4 Darwin/16.7.0
   ```

5. Tap **Save Overrides** on that screen. Reopen **Anisette Client Configuration** and check both values are saved. The fields take the individual lines without the JSON keys or quotation marks. [SideStore settings and sign-in issue](https://github.com/SideStore/SideStore/issues/1744)
6. Go back to **SideStore → Settings → Sign in with Apple ID**. Use the same Apple Account you used in iLoader and complete two-factor authentication if asked.
7. Before adding apps, open **SideStore → My Apps** and tap the **days remaining** badge next to **SideStore** to refresh it. If SideStore prompts you to finish the initial refresh, follow that prompt. Wait for the refresh to complete before proceeding. [SideStore initial refresh instructions](https://docs.sidestore.io/docs/installation/install)

## 7. Add the armcracka Apps source and install

1. To get the source link from GitHub, open **armiko111/SideStore-apps → source.json**, tap **Raw**, and copy the address. The address should start with `raw.githubusercontent.com`. [Open source.json on GitHub](https://github.com/armiko111/SideStore-apps/blob/main/source.json)
2. You can copy the same raw URL here:

   ```text
   https://raw.githubusercontent.com/armiko111/SideStore-apps/main/source.json
   ```

3. With **LocalDevVPN connected** and the iPhone on **Wi-Fi**, open **SideStore → Sources → +**. If your version puts **Sources** inside **Browse**, open it from there. Paste the raw URL in the add-source screen and confirm with **Add** or the **✓** button. You should see **armcracka Apps** in your sources. [SideStore source documentation](https://docs.sidestore.io/docs/advanced/app-sources)
4. Open the source, select **armcracka LangLearn**, and tap **FREE** or **Install**. When installation completes, open it from the Home Screen. The source lists LangLearn at the time of writing.
5. To install a downloaded IPA directly, save it in **Files** and go to **SideStore → My Apps → +**. Select the IPA with **LocalDevVPN and Wi-Fi** connected.

## Refresh and troubleshoot

- **Before seven days are up**, connect **Wi-Fi** and **LocalDevVPN**, open **SideStore → My Apps → Refresh All**, and wait for the expiry counters to renew. A free Apple Account normally allows three active sideloaded apps, including SideStore. [SideStore FAQ](https://docs.sidestore.io/docs/faq.html)
- **Pairing error or error 1414:** Check Wi-Fi and LocalDevVPN first. If both are on, try repairing the pairing file in step 4. [SideStore error codes](https://docs.sidestore.io/docs/troubleshooting/error-codes)
- **Sign-in still shows HTTP 503:** Check that both header values were saved and that **jkcoxson** is selected with rotation off. If it persists, check the [SideStore sign-in issue tracker](https://github.com/SideStore/SideStore/issues/1761) for the current workaround.
- **Source fails to load:** Open the raw URL in Safari. It should show JSON. If the raw file itself fails to load or contains invalid JSON, the source owner needs to fix it on GitHub.
