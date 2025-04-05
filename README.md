# 📸 **Image Logger (Pull IPs)**

## Overview 🔍

Image Logger is a Python-based application that logs information about users when they open a specific image URL. It collects data such as the user’s IP address, geographic location, device details, and more. This data is sent to a Discord webhook for easy monitoring.

👨‍💻 **Created by**: [g4bbdev](https://github.com/silentgng)

⚠️ **Disclaimer**: Please use this tool ethically and responsibly. Make sure you have permission before logging users' IPs.

---

## Features ✨

- 📍 Logs user IP addresses and geographical data (country, region, city, coordinates).
- 🖥️ Captures device information (OS, browser, and user agent).
- 🌐 Supports image URL arguments to change the displayed image.
- 🛡️ Detects and optionally blocks VPNs and bots.
- ✉️ Sends a custom message when the user opens the image.
- 🔄 Option to redirect users to another URL after they view the image.
- 🚨 Sends alerts to your Discord webhook when a new IP is logged.

---

## Installation ⚙️

### 1. Clone this repository:

```bash
git clone https://github.com/silentgng/logger_.git
cd Pull-IPs
```

### 2. Install dependencies:

```bash
pip install requests httpagentparser
```

### 3. Configure the script:

Open the script and edit the `config` dictionary with your custom settings.

- Replace `place_your_webhook_here` with your actual Discord webhook URL.
- Customize other settings like `username`, `color`, `image`, and more.

---

## Configuration 🛠️

Edit the `config` dictionary in the script to modify the following options:

### Webhook & Image Customization 🌄

- **`webhook`**: Your Discord webhook URL to receive the logged IPs.
- **`imageArgument`**: Set to `True` to allow dynamic image URLs via query parameters.
- **`username`**: Set the username for the Discord webhook messages.
- **`color`**: Set the embed color for Discord (hex format).
- **`image`**: Default image URL to display if no custom URL is provided.

### Behavior Options ⚙️

- **`crashBrowser`**: Set to `True` to try crashing or freezing the user’s browser (experimental).
- **`accurateLocation`**: Set to `True` to use GPS for more precise location tracking.
- **`message`**: Customize the message shown when the user opens the image.
- **`vpnCheck`**: Set to manage VPN detection (0 = no check, 1 = notify on VPN, 2 = suppress alerts).
- **`linkAlerts`**: Set to `True` to receive alerts when a link is sent in a chat.
- **`buggedImage`**: Set to `True` to show a loading image preview in Discord.
- **`antiBot`**: Set the bot protection level (0 = no check, 1 = notify on suspected bot, etc.).

### Redirection 🔁

- **`redirect`**: Set to `True` to automatically redirect users to another URL after they open the image.

---

## How It Works 🛠️

When a user opens the image URL, the script logs:

1. **IP Information**:
   - IP address
   - ISP (Internet Service Provider)
   - ASN (Autonomous System Number)
   - Country, region, and city
   - Latitude and longitude
   - Timezone

2. **Device Information**:
   - Operating System
   - Browser
   - User Agent

3. **Optional Features**:
   - If enabled, a custom message is displayed to the user.
   - The user can be redirected to a custom webpage.
   - The image can include a script to attempt to crash the user’s browser.

The collected data is sent to your Discord webhook.

---

## Usage 🚀

### 1. Start the server:

```bash
python3 pull_ips.py
```

### 2. Send the image link:

Once the server is running, use the generated URL to share the image. For example:

```
http://your-server-ip:port/?url=<image_url>
```

When users open this URL, their IP and device information will be logged and sent to your Discord webhook.

---

## Notes 📚

- **Ethical Use**: This tool is for educational purposes only. Make sure to get permission before logging users' IP addresses.
- **Blacklist IPs**: You can blacklist specific IPs by adding them to the `blacklistedIPs` tuple.
- **VPN/Bot Detection**: Use `vpnCheck` and `antiBot` settings to control VPN and bot detection behavior.

---

## License 📄

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Disclaimer ⚠️

This tool can be used to gather IP and metadata, but it must be used responsibly. Misuse of this tool may result in legal consequences. The author is not responsible for any illegal or unethical use of this tool.

---
