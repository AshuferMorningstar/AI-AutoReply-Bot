# AI AutoReply Bot 🤖

An intelligent WhatsApp Web auto-reply bot that uses OpenAI's GPT model to generate contextual responses based on chat history. The bot monitors your WhatsApp Web conversations and automatically replies when it detects new messages from specific contacts.

## 🚀 Features

- **Automated Message Detection**: Monitors WhatsApp Web for new messages
- **AI-Powered Responses**: Uses OpenAI GPT-3.5-turbo to generate contextual replies
- **Persona Customization**: Bot responds as "Naruto" with a specific personality (coder from India)
- **Smart Chat Analysis**: Analyzes chat history to provide relevant responses
- **Screen Automation**: Uses PyAutoGUI for interacting with WhatsApp Web interface
- **Clipboard Integration**: Seamlessly copies and pastes messages

## 🛠️ Tools & Technologies Used

### Core Technologies
- **Python 3.7+** - Main programming language
- **OpenAI API** - GPT-3.5-turbo model for intelligent response generation
- **WhatsApp Web** - Target platform for automation

### Python Libraries
- **PyAutoGUI** - Screen automation and mouse/keyboard control
- **Pyperclip** - Clipboard operations for copying and pasting text
- **OpenAI Python SDK** - Official OpenAI API client
- **Time** - Built-in module for delays and timing control

### Development Tools
- **Chrome Browser** - Required for WhatsApp Web interface
- **Screen Coordinate Detection** - Custom utility for UI element positioning
- **Real-time Chat Monitoring** - Continuous message detection system

## 📋 Requirements

- Python 3.7+
- OpenAI API key
- WhatsApp Web opened in Chrome browser
- Stable internet connection

## 🛠️ Installation

1. **Clone the repository** (or download the files):
   ```bash
   git clone <repository-url>
   cd "AI AutoReply Bot"
   ```

2. **Install required packages**:
   ```bash
   pip install pyautogui openai pyperclip
   ```

3. **Set up OpenAI API key**:
   - Get your API key from [OpenAI Platform](https://platform.openai.com/api-keys)
   - Replace `<Your Key Here>` in both `02_openai.py` and `03_bot.py` with your actual API key

## 📁 Project Structure

```
AI AutoReply Bot/
├── 01_get_cursor.py    # Utility to get mouse cursor coordinates
├── 02_openai.py        # OpenAI API testing and configuration
├── 03_bot.py          # Main bot application
└── README.md          # Project documentation
```

## 🔧 Setup Instructions

### 1. Configure Screen Coordinates

The bot uses specific screen coordinates to interact with WhatsApp Web. You may need to adjust these based on your screen resolution and browser setup:

1. **Run the cursor position utility**:
   ```bash
   python 01_get_cursor.py
   ```
   Move your mouse to different positions on WhatsApp Web and note the coordinates.

2. **Update coordinates in `03_bot.py`**:
   - Chrome icon position: `pyautogui.click(1639, 1412)`
   - Chat selection area: `pyautogui.moveTo(972,202)` to `pyautogui.dragTo(2213, 1278...)`
   - Message input box: `pyautogui.click(1808, 1328)`

### 2. Test OpenAI Integration

```bash
python 02_openai.py
```

This will test your OpenAI API connection and show you how the bot generates responses.

### 3. Customize Bot Personality

In `03_bot.py`, you can modify the system prompts to change the bot's personality:

```python
{"role": "system", "content": "You are a person named Naruto who speaks hindi as well as english..."}
```

## 🚀 Usage

1. **Open WhatsApp Web** in Chrome browser
2. **Position the browser window** so that the chat area is visible
3. **Run the bot**:
   ```bash
   python 03_bot.py
   ```

The bot will:
- Monitor the chat every 5 seconds
- Detect when the specified sender ("Rohan Das" by default) sends a new message
- Generate an AI response using the chat history
- Automatically type and send the reply

## ⚙️ Configuration

### Change Target Sender

In `03_bot.py`, modify the sender name:
```python
if is_last_message_from_sender(chat_history, sender_name="Your Friend's Name"):
```

### Adjust Monitoring Interval

Change the sleep time between checks:
```python
time.sleep(5)  # Check every 5 seconds
```

### Modify AI Model

You can switch to different OpenAI models:
```python
model="gpt-4"  # or "gpt-3.5-turbo"
```

## ⚠️ Important Notes

- **Screen Resolution**: Coordinates are hardcoded and may need adjustment for different screen sizes
- **API Costs**: Each response uses OpenAI API credits
- **Rate Limits**: Be mindful of OpenAI's rate limits
- **Privacy**: This bot reads your chat messages to generate responses
- **WhatsApp ToS**: Using automation tools may violate WhatsApp's Terms of Service

## 🐛 Troubleshooting

### Bot not detecting messages
- Check if WhatsApp Web is properly loaded
- Verify screen coordinates are correct for your setup
- Ensure the chat window is visible and not minimized

### API errors
- Verify your OpenAI API key is valid
- Check your API usage limits
- Ensure stable internet connection

### Mouse/keyboard automation issues
- Run Python with appropriate permissions
- Check if other applications are interfering
- Adjust timing delays if actions are too fast

## 🤝 Contributing

Feel free to fork this project and submit pull requests for improvements such as:
- Better coordinate detection
- Multiple platform support
- Enhanced error handling
- GUI interface
- Configuration file support

## 📄 License

This project is for educational purposes. Please ensure you comply with:
- WhatsApp's Terms of Service
- OpenAI's Usage Policies
- Local laws regarding automation and privacy

## ⚡ Disclaimer

This bot is created for educational and personal use only. The authors are not responsible for any misuse or violations of terms of service. Use responsibly and respect others' privacy.