# OMG TV & OMG+ TV - Stremio Addon

[🇮🇹 Leggi in italiano](leggimi.md)

A Stremio addon to add M3U playlist (IPTV) channels with EPG support to your catalog.
For the PLUS version with custom playlist support, visit: https://github.com/mccoy88f/OMG-Plus-TV-Stremio-Addon

⚠️⚠️⚠️ **VERY IMPORTANT! NEW REBRANDED & UPDATED VERSION FEB 2025 IS HERE:**
This will be abandoned and then closed!
https://www.reddit.com/r/StremioAddons/comments/1j0gzae/tv_on_stremio_omg_premium_tv_m3u_playlist_addon/
NEW REPO: https://github.com/mccoy88f/OMG-Premium-TV

IMPORTANT: First of all...

<a href="https://www.buymeacoffee.com/mccoy88f"><img src="https://img.buymeacoffee.com/button-api/?text=Buy me a beer&emoji=🍺&slug=mccoy88f&button_colour=FFDD00&font_colour=000000&font_family=Bree&outline_colour=000000&coffee_colour=ffffff" /></a>

[You can also buy me a beer with PayPal 🍻](https://paypal.me/mccoy88f?country.x=IT&locale.x=it_IT)

## 🌟 Main Features

### Core
- Channel browsing by categories
- Channel search by name
- Automatic channel number sorting
- Data caching with auto-update
- Multiple playlist support
- Automatic duplicate stream management
- Smart cache with 12-hour auto-update

### EPG (Electronic Program Guide)
- EPG support with detailed information
- Currently airing program display
- Upcoming programs list
- Multiple EPG support
- Channel ID remapping system
- EPG cache with 12-hour auto-update
- Compressed EPG file support (gz)

### Streaming
- Direct HLS stream support
- Unencrypted DASH MPD stream support
- MediaFlow Proxy integration
- Custom User-Agent management
- Custom headers for each stream

## 🚀 Deployment Options

### 1. Deploy on Render.com
[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/mccoy88f/OMG-plus-TV-Stremio-Addon)

1. Click the button above (requires a Render account)
2. Select 'main' branch (use the other ones only for test)
3. Configure required environment variables

### 2. Deploy on Hugging Face
1. Create a new Space on Hugging Face
2. Select "Docker" as template
3. Use the provided Dockerfile (Dockerfile.hf in this repo)
4. Configure environment variables in Space settings

## 🛠️ Environment Variables Configuration

### Basic Configuration
- `M3U_URL`: M3U playlist URL (Plus version only)
  - Supports both single playlist and URL list file
  - Default: Hardcoded URL in base version
  
- `EPG_URL`: EPG guide URL (Plus version only)
  - Supports both single EPG file and URL list file
  - Supports compressed .gz files
  - Default: Hardcoded URL in base version

- `ID_SUFFIX`: Suffix for channel IDs
  - Example: 'it' will add .it to channel IDs without ID
  - If not set or empty, no suffix will be added
  - No default value

### EPG Configuration
- `ENABLE_EPG`: Enable/disable EPG 
  - Values: 'no' to disable
  - Default: enabled
  
- `TIMEZONE_OFFSET`: Timezone offset for EPG
  - Format: '+1:00' or '-2:00'
  - Default: '+1:00'

### Proxy Configuration
- `PROXY_URL`: MediaFlow Proxy URL
  - Optional
  - Required for some devices/browsers

- `PROXY_PASSWORD`: Proxy password
  - Required if PROXY_URL is set

- `FORCE_PROXY`: Force proxy usage
  - Values: 'yes' to enable
  - Removes direct streams when active

### Deployment Configuration
- `PORT`: Server port
  - Render.com: Default 10000
  - Hugging Face: Default 7860
  
- `HOST`: Server host
  - Hugging Face: Default '0.0.0.0'

- `BRANCH`: Repository branch
  - Value: main (use the other ones only for test)
  - Used in Hugging Face deployment

## 🔄 Changelog

### v3.3.0
- Improved remapping
- Multiple category/genre for same channel if set in m3u playlist
- Better epg parsing, now all id is managed lowercase (everywhere)

### v3.2.0
- Added compressed EPG file support
- Added ID_SUFFIX variable for custom channel IDs
- Improved EPG timezone handling
- Cache and performance optimization
- Hugging Face deployment support
- Minor fixes and stability improvements

### v3.0.0
- Improved EPG management
- DASH MPD stream support
- Channel ID remapping system
- Hugging Face deployment support

### v2.5.0
- Multi-playlist and multi-EPG management
- Improved genre/group handling
- Same ID channel unification
- Large EPG file support

## ⚠️ Important Notes
- EPG files larger than 5/7 MB might cause issues on Render.com
- On Render.com, use [uptime robot](https://uptimerobot.com/) to prevent server standby
- Some streams might require proxy for certain devices
- Cache automatically updates every 12 hours

## 📦 Local Installation

1. Clone the repository
```bash
git clone https://github.com/mccoy88f/OMG-TV-Stremio-Addon.git
```

2. Install dependencies
```bash
npm install
```

3. Start the addon
```bash
npm start
```

## 👏 Acknowledgments
- FuriousCat for the OMG name idea
- [Stremio Italia](https://www.reddit.com/r/Stremio_Italia/) team
- [Stremio ITA](https://t.me/Stremio_ITA) Telegram community
- Iconic Panda for [icon](https://www.flaticon.com/free-icon/tv_18223703?term=tv&page=1&position=2&origin=tag&related_id=18223703)

## 📜 License
Project released under MIT license.

## ⚠️ Disclaimer
- Not responsible for illegal use of the addon
- Content provided by third parties
- No guarantee on channel availability
