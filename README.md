# Tdl - Telegram Downloader Bot

## Overview

Tdl is a powerful Telegram bot designed for downloading media content from various sources. Built with Python using the Pyrogram library, it supports batch downloading from text files containing URLs, with customizable resolutions and formats. The bot leverages yt-dlp for robust media extraction and supports multiple platforms including YouTube, Vimeo, and more.

## Features

- **Batch Downloading**: Download multiple videos from a text file containing URLs
- **Resolution Selection**: Choose from various resolutions (144p to 1080p)
- **Progress Tracking**: Real-time download progress with progress bars
- **Telegram Integration**: Seamless interaction via Telegram bot interface
- **Error Handling**: Robust error handling for failed downloads
- **Logging**: Comprehensive logging for monitoring and debugging
- **MongoDB Support**: Database integration for user data and download history

## Prerequisites

Before running this bot, ensure you have the following:

- Python 3.8 or higher
- A Telegram Bot Token (obtained from [@BotFather](https://t.me/botfather))
- Telegram API ID and API Hash (from [my.telegram.org](https://my.telegram.org))
- MongoDB database (optional, for advanced features)
- Required Python packages (listed in `requirements.txt`)

## Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/anjalidshukla/Tdl.git
cd Tdl
```

### Step 2: Install Dependencies

Install the required Python packages using pip:

```bash
pip install -r requirements.txt
```

### Step 3: Configure Environment Variables

Create a `.env` file in the root directory or set environment variables directly. Add the following variables:

```env
API_ID=your_telegram_api_id
API_HASH=your_telegram_api_hash
BOT_TOKEN=your_bot_token
LOG_CHANNEL=your_log_channel_id  # Optional: Channel ID for logging
MONGO_URI=your_mongodb_connection_string  # Optional: For database features
```

**Note**: Never commit your `.env` file or expose sensitive information in your code.

### Step 4: Set Up Bot Credentials

Edit the `vars.py` file to include your credentials:

```python
API_ID = your_api_id
API_HASH = "your_api_hash"
BOT_TOKEN = "your_bot_token"
```

Alternatively, use environment variables as shown above.

## Usage

### Running the Bot Locally

1. Ensure all dependencies are installed and environment variables are set.
2. Run the bot using Python:

```bash
python main.py
```

3. The bot will start and connect to Telegram. You can interact with it via the Telegram app.

### Bot Commands

- `/start`: Initialize the bot and display welcome message
- `/TXT`: Start the download process from a text file
- `/stop`: Stop the bot and restart it

### Download Process

1. Send `/TXT` command to the bot
2. Upload a text file containing URLs (one URL per line)
3. Specify the starting index for downloads
4. Enter a batch name for the download session
5. Select the desired resolution
6. The bot will process and download each video, sending progress updates

## Project Structure

```
Tdl/
├── app.py              # Flask web app (for health checks or web interface)
├── core.py             # Core download logic and helper functions
├── logs.py             # Logging utilities
├── main.py             # Main bot script
├── utils.py            # Utility functions (progress bars, etc.)
├── vars.py             # Configuration variables
├── Dockerfile          # Docker container configuration
├── Procfile            # Heroku/Render deployment configuration
├── requirements.txt    # Python dependencies
└── README.md           # This file
```

## Configuration

### Environment Variables

- `API_ID`: Your Telegram API ID
- `API_HASH`: Your Telegram API Hash
- `BOT_TOKEN`: Your Telegram Bot Token
- `LOG_CHANNEL`: Telegram channel ID for logging (optional)
- `MONGO_URI`: MongoDB connection string (optional)
- `PORT`: Port for Flask app (default: 10000)

### Bot Settings

Modify settings in `vars.py` or through environment variables to customize:
- Download paths
- Resolution options
- Logging levels
- Database connections

## Deployment

### Local Deployment

Follow the installation steps above and run `python main.py`.

### Docker Deployment

1. Build the Docker image:

```bash
docker build -t tdl-bot .
```

2. Run the container:

```bash
docker run -e API_ID=your_api_id -e API_HASH=your_api_hash -e BOT_TOKEN=your_bot_token tdl-bot
```

### Cloud Deployment (Render)

See the deployment section below for detailed Render instructions.

## Troubleshooting

### Common Issues

1. **Bot not responding**: Check if API credentials are correct and bot token is valid
2. **Download failures**: Ensure URLs are valid and supported by yt-dlp
3. **Permission errors**: Check file permissions for download directories
4. **MongoDB connection issues**: Verify MongoDB URI and network access

### Logs

Check `logs.py` for logging configuration. Logs are output to console and can be redirected to files or Telegram channels.

### Debug Mode

Enable debug logging by setting the log level in your environment or code.

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and test thoroughly
4. Commit your changes: `git commit -am 'Add new feature'`
5. Push to the branch: `git push origin feature-name`
6. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Disclaimer

This bot is for educational and personal use only. Ensure you comply with the terms of service of the platforms you're downloading from and respect copyright laws. The developers are not responsible for misuse of this software.

## Support

For support or questions:
- Create an issue on GitHub
- Check the logs for error messages
- Ensure all prerequisites are met

---

**Developed by: MOHINI**