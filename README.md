# gpt-discord-chatbot

A simple Python-based Discord chatbot that uses GPT-3 for natural language processing and text generation.

## Overview

This repository contains a basic implementation of a Discord chatbot using Python and GPT-3. The chatbot uses the discord.py library to interact with the Discord API and handle events such as messages, reactions, and more. It also uses OpenAI's GPT-3 to process natural language and generate text based on the user's input. It can be used to create custom commands, automate tasks, and integrate with external APIs.
## Features

- Custom command
- Automated tasks
- Integration with external APIs
- Natural Language Processing and Text Generation using GPT-3

## Requirements

- Python 3.7 or later
- `discord.py` library
- OpenAI API Key
- Discord bot token

## Usage

1. Clone the repository:

    ```
    git clone https://github.com/shamspias/gpt-discord-chatbot
    ```

2. Install the dependencies into virtual env:

    ```
    pip install -r requirements.txt
    ```

3. Replace .env.example into .env and give the API keys and discord client and secreat in `.env` with your Discord bot token.

4. Run the bot:

    ```
    python -m src.main.py
    ```

5. The bot should now be running and connected to your Discord server. You can interact with it by sending messages or
using custom commands.

## Custom Command

you can add custom command by adding function in the `bot.py` file and mention the function name in the `on_message()`
event.

## Limitations

This sample chatbot has some limitations and is just for demonstration purposes.

It has basic functionality and does not handle any form of natural language processing, sentiment analysis, or other
advanced features.
It does not have any form of UI and just accepts and returns json data.

## Contributions

If you find any bugs or would like to add new features, please feel free to open a pull request or an issue.

## License

This repository is released under the MIT license. See [LICENSE](https://github.com/shamspias/gpt-discord-chatbot/blob/main/LICENSE) for more details.

Please note that you will need to create a bot account on Discord and invite it to your server before you can use it.
you can find more information about creating a bot account on the [Discord Developer Portal](https://discord.com/developers/docs/intro)

## Thanks

1. [OpenAI](https://github.com/openai/gpt-discord-bot)

## Errors

1. ```
   Discord.errors.PrivilegedIntentsRequired: Shard ID None is requesting privileged intents that have not been explicitly enabled in the developer portal" occurs when your Discord bot is trying to use privileged intents, but they have not been enabled in the Discord developer portal.
   ```
**Solution**:

Privileged intents are a set of additional intents that provide access to additional data and events. They include access to direct messages, presence updates, and more. These intents are only available to verified bot developers and require explicit approval from Discord.

To fix this error, you need to go to your Discord developer portal, and enable the privileged intents that your bot is trying to use.

1. Go to the developer portal at https://discord.com/developers/applications
2. Select the bot application
3. Navigate to the "Bot" section
4. Scroll down to the "Privileged Gateway Intents" section
5. Enable the intents that your bot requires
6. Click on "Save Changes"

## Extra

1. If you want to work for only specific server then uncomment code under `src/utils.py`
   ```
    if guild.id and guild.id not in ALLOWED_SERVER_IDS:
        # not allowed in this server
        logger.info(f"Guild {guild} not allowed")
        return True
   ```
