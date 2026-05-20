# 🤖 Charlton-MD WhatsApp Bot

A powerful WhatsApp automation bot built with Node.js and [Baileys](https://github.com/WhiskeySockets/Baileys) library.

## ✨ Features

- ✅ **Multi-command support** - Extensible command architecture
- ✅ **Session management** - QR code or session ID authentication
- ✅ **Auto-reconnect** - Automatic reconnection on disconnect
- ✅ **Typing indicators** - Shows "typing..." status
- ✅ **Error handling** - Robust error management
- ✅ **Production-ready** - Ready for deployment

## 🔗 Fork Sites & Resources

### **Session ID Generators (Choose One):**
1. **[BK9 Session Generator](https://bk9session.vercel.app/)** ⭐ **ACTIVE & RECOMMENDED**
   - Simple UI for pairing code or QR code
   - Fast and reliable
   
2. **[ArchMD Bot Generator](https://archmd-bot.vercel.app/)** (Backup option)
   - Alternative if BK9 is down

3. **[GitHub - SESSION-GENERATOR](https://github.com/Itxxwasi/SESSION-GENERATOR)**
   - Open-source, self-deployable option

## 📦 Installation

```bash
git clone https://github.com/otienojunior806-eng/Charlton-md.git
cd Charlton-md
npm install
```

## 🔐 Session Management

### Option 1: Using QR Code (Quick Start)

```bash
cp .env.example .env
npm start
```

Scan the QR code with WhatsApp and you're done!

### Option 2: Using Session ID (Recommended for Headless/Server)

1. Go to **[BK9 Session Generator](https://bk9session.vercel.app/)**
2. Enter your WhatsApp number
3. Click "Get Pair Code"
4. Copy the session ID from the site
5. Add to `.env`:

```env
SESSION_ID=your_session_id_here
```

6. Start the bot:

```bash
npm start
```

## 📋 Built-in Commands

| Command | Description | Example |
|---------|-------------|----------|
| `hello` | Greet the bot | `hello` |
| `echo [text]` | Echo back message | `echo Hello World` |
| `ping` | Check bot status | `ping` |
| `time` | Get current time | `time` |
| `help` or `?` | Show help menu | `help` |

## 🚀 Heroku Deployment

### Method 1: Using Heroku CLI

```bash
# Install Heroku CLI
# https://devcenter.heroku.com/articles/heroku-cli

heroku login
heroku create your-app-name
heroku config:set SESSION_ID=your_session_id
git push heroku main
heroku logs --tail
```

### Method 2: Using Heroku Dashboard

1. Go to [Heroku Dashboard](https://dashboard.heroku.com/)
2. Click "New" → "Create new app"
3. Give it a name and create
4. Go to "Deploy" tab
5. Connect to your GitHub repository
6. Enable "Automatic Deploys"
7. Go to "Settings" → "Config Vars"
8. Add `SESSION_ID` with your session value
9. Click "Deploy Branch"

### Heroku Config Variables

Add these to your Heroku app:

```
SESSION_ID=your_session_id_here
NODE_ENV=production
```

## 🔧 Environment Variables

Create a `.env` file:

```env
# WhatsApp Session (optional - use QR code if not set)
SESSION_ID=

# Bot settings
BOT_NAME=Charlton-MD
BOT_PREFIX=.
NODE_ENV=development
```

## 📁 Project Structure

```
Charlton-md/
├── bot.js              # Main bot file
├── bot-advanced.js     # Advanced version with command handler
├── commands.js         # Command management module
├── package.json        # Dependencies
├── .env.example        # Environment template
├── .gitignore          # Git ignore rules
├── Procfile            # Heroku process file
└── README.md           # This file
```

## ⚙️ Configuration

### Adding Custom Commands

Edit `commands.js`:

```javascript
commands.set('mycommand', {
  execute: (msg, args) => {
    msg.reply('My response here!');
  },
  description: 'My custom command description'
});
```

## 🐛 Troubleshooting

### Session ID Expired
- Generate a new session ID from [BK9 Session Generator](https://bk9session.vercel.app/)
- Update `.env` with new SESSION_ID
- Restart the bot

### Bot Not Responding
- Check internet connection
- Verify WhatsApp is not logged in on another device
- Delete `session_folder` and restart bot

### Heroku App Crashes
- Check logs: `heroku logs --tail`
- Verify SESSION_ID is set correctly
- Ensure dyno has enough RAM

## 📝 Available Scripts

```bash
npm start              # Start the bot
npm run start-advanced # Start advanced version
```

## ⚠️ Security & Safety

- **Never share your session ID publicly**
- Keep `.env` file in `.gitignore`
- Use environment variables for sensitive data
- Follow WhatsApp's Terms of Service
- Use responsibly to avoid account suspension

## 📄 License

MIT License - feel free to use and modify

## 🤝 Contributing

Contributions welcome! Fork, create a branch, and submit a pull request.

## 📞 Support

- Check existing issues: [GitHub Issues](https://github.com/otienojunior806-eng/Charlton-md/issues)
- Create new issue with details and error logs
- Join WhatsApp bot communities for help

---

**Built with ❤️ using Node.js & Baileys**

*Last Updated: 2026-05-20*