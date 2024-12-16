# **uBlock Origin Advanced Configuration Guide**

This guide explains how to configure uBlock Origin to block Twitch ads using advanced settings and a custom script.

## **Prerequisites**  
Ensure the following:  
- uBlock Origin is installed in your browser.  
- Basic familiarity with browser extensions.  
- A Twitch account for testing.

## **Step 1: Enable Advanced Settings in uBlock Origin**

### **1. Open uBlock Origin Dashboard**
- Click the **uBlock Origin** icon in your browser's toolbar.  
- Click the **gear icon** ⚙️ to open the **Dashboard**.

### **2. Enable Advanced User Mode**
- Navigate to the **Settings** tab.  
- Scroll down and check the box for **"I am an advanced user"**.  
- A **cogwheel** ⚙️ will appear next to the checkbox.  

### **3. Open the Advanced Settings Editor**
- Click the **cogwheel** to open the **advanced settings editor**.  

## **Step 2: Modify Advanced Settings**

### **1. Locate the `userResourcesLocation` Parameter**
- In the **advanced settings editor**, find the line for `userResourcesLocation`.  
- By default, this is set to `unset`.

### **2. Add the Custom Script URL**
- Replace `unset` with the following URL:
   ```plaintext
   https://raw.githubusercontent.com/pixeltris/TwitchAdSolutions/master/video-swap-new/video-swap-new-ublock-origin.js
   ```

### **3. Add Multiple URLs (if Needed)**
- If another script URL is already specified, append a space and then add the new URL.  
   Example:
   ```plaintext
   userResourcesLocation https://existing-url.com/script.js https://raw.githubusercontent.com/pixeltris/TwitchAdSolutions/master/video-swap-new/video-swap-new-ublock-origin.js
   ```

### **4. Save the Changes**
- Click **"Apply changes"** or save the editor.

## **Step 3: Restart uBlock Origin**

### **1. Restart the Extension**
- Go to your browser’s **Extension Manager**:  
   - **Chrome**: Visit `chrome://extensions/`.  
   - **Firefox**: Visit `about:addons`.  
- Disable and re-enable the **uBlock Origin** extension.

### **2. Restart the Browser**
- As an alternative, restart your browser completely to ensure changes take effect.


## **Step 4: Test the Configuration**

### **1. Open Twitch**
- Visit [https://www.twitch.tv](https://www.twitch.tv) and start watching a live stream.

### **2. Monitor Ad Behavior**
- Check if:  
   - Ads are completely blocked.  
   - Ads are replaced with a clean video stream.  

### **3. Verify the Script is Loaded**
- Open the uBlock Origin **Logs** (Dashboard > Logs) to confirm that the custom script is applied.  

## **Step 5: Troubleshooting**

### **1. Ads Still Appear**
- Verify the `userResourcesLocation` URL:
   - Open the advanced settings editor and confirm no typos in the URL.  
- Ensure the script URL is accessible by visiting it directly in your browser.

### **2. Extension Not Applying Changes**
- Double-check that you clicked **"Apply changes"** after modifying the advanced settings.  
- Restart the browser and reload Twitch.

### **3. Conflicting Filters**
- Disable other uBlock Origin filters that may conflict with the custom script.  

### **4. Check for Updates**
- Ensure the script is up-to-date by checking the **[TwitchAdSolutions GitHub Repository](https://github.com/pixeltris/TwitchAdSolutions)**.  

## **Tips**

1. **Monitor Logs:**  
   - Use the **Logs** feature in the uBlock Origin Dashboard to monitor requests and ensure the script is active.

2. **Update the Script Regularly:**  
   - Twitch updates its ad delivery mechanisms frequently. Stay up-to-date with the latest version of the script.

3. **Test on Multiple Browsers:**  
   - If the script doesn’t work on one browser, test it on another supported browser (e.g., Chrome or Firefox).

4. **Combine with DNS Blocking:**  
   - Use a service like **NextDNS** to block Twitch-related ad domains for an extra layer of protection.

## **Credits**  
- **Custom Script Author**: [Pixeltris](https://github.com/pixeltris)  
- **uBlock Origin**: [uBlock Origin on GitHub](https://github.com/gorhill/uBlock)
