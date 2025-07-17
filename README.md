# TgBoter - Telegram Chatbot

https://github.com/sakshamagarwalm2/TgBot/blob/main/Screenshot%202025-07-17%20133204.png

## Overview
TgBoter is a Telegram chatbot built using Python, the `aiogram` library, and Azure AI Inference for natural language processing. This project was developed as part of an IIT Jammu assignment to create an interactive chatbot capable of handling text messages and responding intelligently using a GPT model hosted on Azure. The bot supports basic commands like `/start` and `/help` and processes user text inputs with contextual responses.

## Features
- **Command Handling**: Supports `/start` and `/help` commands for user interaction.
- **Text Processing**: Uses Azure AI Inference with a GPT model to generate responses to user messages.
- **Context Management**: Stores previous responses to maintain conversation context (basic implementation).
- **Asynchronous Design**: Built with `aiogram` for efficient handling of Telegram API requests.
- **Colab Compatibility**: Designed to run in Google Colab with proper event loop management.

## Prerequisites
- Python 3.7+
- A Telegram bot token from [BotFather](https://t.me/BotFather)
- Azure AI Inference endpoint and credentials
- Google Colab environment (optional, for running in Colab)

## Installation
1. **Clone the Repository** (if hosted on GitHub):
   ```bash
   git clone https://github.com/sakshamagarwalm2/TgBot
   cd TgBoter
   ```

2. **Install Dependencies**:
   ```bash
   pip install -U aiogram
   pip install azure-ai-inference
   ```

3. **Set Environment Variables**:
   - In Google Colab, use the `userdata` module to set environment variables:
     ```python
     from google.colab import userdata
     os.environ['TELEGRAM_BOT_TOKEN'] = userdata.get('TELEGRAM_BOT_TOKEN')
     os.environ['GITHUB_TOKEN'] = userdata.get('GITHUB_TOKEN')
     ```
   - Alternatively, set them in your environment or a `.env` file.

4. **Run the Bot**:
   - Execute the Jupyter notebook (`TgBoter.ipynb`) in Google Colab or a local Jupyter environment.
   - Ensure the event loop is handled correctly for asynchronous execution.

## Usage
1. Start the bot by running the notebook or script.
2. Interact with the bot on Telegram:
   - Send `/start` to receive a welcome message.
   - Send `/help` to see available commands.
   - Send any text message to get a response powered by Azure AI Inference.
3. The bot stores the latest response in a basic context object for potential future enhancements.

## Code Structure
- **Dependencies**: Imports `aiogram`, `azure-ai-inference`, and `asyncio` for bot functionality.
- **Command Handlers**: `/start` and `/help` commands provide basic interaction.
- **Text Handler**: Processes user messages using Azure's GPT model.
- **Main Loop**: Manages the bot's polling mechanism with proper event loop handling for Colab.

## Limitations
- The current context management is basic and only stores the latest response.
- Audio and image processing are mentioned in the `/help` command but not implemented.
- Requires valid Azure credentials and a Telegram bot token to function.
- Designed for Colab; local execution may require event loop adjustments.

## Future Improvements
- Implement audio and image processing as indicated in the `/help` command.
- Enhance context management to store full conversation history.
- Add error handling for network issues and rate limits.
- Deploy to a server for continuous operation instead of Colab.

## Acknowledgments
- Developed as part of an IIT Jammu assignment.
- Powered by `aiogram` for Telegram bot development and Azure AI Inference for NLP.
- Thanks to the open-source community for providing robust libraries.

## License
This project is licensed under the MIT License.
