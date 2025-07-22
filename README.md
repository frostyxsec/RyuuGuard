# RyuuGuard

Simple Open Source Server Engine Security Monitor IDSA

## Features

- Real-time monitoring of Server access and error logs
- Brute force attack detection
- Suspicious activity detection
- Unauthorized access detection
- Malware detection
- Binary data detection
- SSH login monitoring
- Suspicious shell command detection
- Telegram notifications

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/RyuuGuard.git
cd RyuuGuard

# Make the script executable
chmod +x ryuuguard

# Move to system path (requires root)
sudo mv ryuuguard /usr/bin/ryuuguard
```

## Usage

```bash
# Start a new tmux session for RyuuGuard
tmux new-s ryuuguard

# Run RyuuGuard
ryuuguard
```

### Commands

- `ryuuguard` - Start monitoring
- `ryuuguard --status` - Check if running
- `ryuuguard --logs` - View recent alerts
- `ryuuguard --test` - Test Telegram setup
- `ryuuguard --init` - Create config file
- `ryuuguard --help` - Show help message

## Telegram Configuration

1. Create a new bot using [@BotFather](https://t.me/BotFather) on Telegram
2. Get your bot token from BotFather
3. Start a chat with your bot
4. Get your chat ID using [@userinfobot](https://t.me/userinfobot) or by sending a message to [@get_id_bot](https://t.me/get_id_bot)
5. Edit the configuration file:

```bash
# Create default config if it doesn't exist
ryuuguard --init
```

```bash
# Change the log path
LOG_DIR="/var/log/nginx"
```

```bash
# Edit the config before installing
nano /usr/bin/ryuuguad
# Edit the config file
nano /etc/ryuuguard.conf
```

Add your Telegram credentials to the config file:

```
# RyuuGuard Configuration File
# Edit these values with your Telegram Bot credentials

# Telegram Bot Token (get from @BotFather)
TELEGRAM_BOT_TOKEN="YOUR_BOT_TOKEN_HERE"

# Telegram Chat ID (your chat ID or group ID)
TELEGRAM_CHAT_ID="YOUR_CHAT_ID_HERE"

# Brute Force Detection Settings
BRUTE_FORCE_THRESHOLD=10
BRUTE_FORCE_WINDOW=300

# Additional Settings
MAX_FAILED_LOGINS=5
NOTIFICATION_COOLDOWN=60
```

6. Test your Telegram configuration:

```bash
ryuuguard --test
```

## License

[MIT](LICENSE)

## Download
<a href="https://github.com/frostyxsec/RyuuGuard/releases/tag/release">Click Here</a>
