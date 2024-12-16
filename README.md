# **uBlock Origin Advanced Configuration Guide**

This guide explains how to configure **uBlock Origin** to block Twitch ads using custom filters, advanced settings, and a custom script.

## **Prerequisites**  
Ensure the following:  
- uBlock Origin is installed in your browser.  
- Basic familiarity with browser extensions.  
- A Twitch account for testing.

## **Step 1: Add Custom Filters for Twitch**

### **1. Open the “My Filters” Section**
- Click the **uBlock Origin** icon in your browser's toolbar.  
- Click the **gear icon** ⚙️ to open the **Dashboard**.  
- Go to the **"Filter lists"** tab.  
- Scroll down to the **"My filters"** section.

### **2. Add the Following Custom Filter**
Input the following filter to block Twitch video ads:  
```plaintext
twitch.tv##+js(twitch-videoad)
```

### **3. Save Changes**
- Click **"Apply changes"** at the top of the dashboard to save the filter.

## **Step 2: Enable Advanced Settings in uBlock Origin**

### **1. Open Advanced Settings**
- In the Dashboard, navigate to the **"Settings"** tab.  
- Scroll down and check the box for **"I am an advanced user"**.  
- A **cogwheel** ⚙️ will appear next to the checkbox.  
- Click the **cogwheel** to open the **advanced settings editor**.

## **Step 3: Modify Advanced Settings**

### **1. Locate the `userResourcesLocation` Parameter**
- In the **advanced settings editor**, find the line for `userResourcesLocation`.  
- By default, this is set to `unset`.

### **2. Add the Custom Script URL**
- Replace `unset` with the following URL:
   ```plaintext
   https://raw.githubusercontent.com/pixeltris/TwitchAdSolutions/master/video-swap-new/video-swap-new-ublock-origin.js
   ```

### **3. Save the Changes**
- Click **"Apply changes"** or save the editor.

## **Step 4: Restart uBlock Origin**

### **1. Restart the Extension**
- Open your browser’s **Extension Manager**:  
   - **Chrome**: Visit `chrome://extensions/`.  
   - **Firefox**: Visit `about:addons`.  
- Disable and re-enable the **uBlock Origin** extension.

### **2. Restart the Browser**
- Alternatively, restart your browser completely to ensure changes take effect.

## **Step 5: Test the Configuration**

### **1. Open Twitch**
- Visit [https://www.twitch.tv](https://www.twitch.tv) and start watching a live stream.

### **2. Monitor Ad Behavior**
- Check if:  
   - Ads are completely blocked.  
   - Ads are replaced with a clean video stream.

### **3. Verify the Script and Filter**
- Open the **uBlock Origin Logs**:  
   - Go to **Dashboard > Logs** to confirm that the custom script and filters are applied correctly.

## **Step 6: Troubleshooting**

### **1. Ads Still Appear**
- Verify the `userResourcesLocation` URL in the **advanced settings**.  
- Ensure the custom filter `twitch.tv##+js(twitch-videoad)` is saved under “My Filters.”

### **2. Check Script Accessibility**
- Confirm the script URL is accessible by visiting it directly:  
   [TwitchAdSolutions Script](https://raw.githubusercontent.com/pixeltris/TwitchAdSolutions/master/video-swap-new/video-swap-new-ublock-origin.js).

### **3. Conflicting Filters**
- Disable other conflicting filters under the “Filter lists” tab.

### **4. Update the Script**
- Twitch frequently updates its ad-delivery system. Ensure the script is up-to-date by visiting the [TwitchAdSolutions GitHub Repository](https://github.com/pixeltris/TwitchAdSolutions).

## **Tips**

1. **Monitor Logs:**  
   Use the Logs feature in the uBlock Origin Dashboard to track requests and ensure the script and filters are applied.

2. **Test on Different Browsers:**  
   Test the configuration on browsers like Firefox and Chrome to compare performance.

3. **Combine with DNS Blocking:**  
   Use services like **NextDNS** to block known Twitch ad-related domains for additional privacy.

4. **Stay Updated:**  
   Regularly check the script and filter for updates as Twitch evolves its ad systems.

