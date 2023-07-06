# Telegram Message Auto Forwarder & Downloader

This is a Python script that allows you to forward file messages and photos from a Telegram channel to your saved messages. It uses the Telethon library for interacting with the Telegram API.

## Prerequisites

Before running the script, make sure you have the following prerequisites:

- Python 3.x installed
- Telegram API credentials: API ID and API hash (obtain them from https://my.telegram.org/auth)
- Access to the Telegram channel from which you want to forward files
- The `telethon` library installed
```bash
pip3 install telethon py7zr rarfile
```

## Important Note

This code has only been tested in Google Colab. If you plan to run it outside of Google Colab, you may need to make modifications to adapt it to your environment. Specifically, you might need to adjust the download path, ensure the necessary dependencies are installed, and set up appropriate access credentials. 
 
If you want to forward messages from a private channel, you need to follow these additional steps:

1. Run the "Get Private Channel ID" cell in the script to obtain the private channel ID.
2. Copy the obtained private channel ID.
3. Proceed to the "Forward Message" cell in the script and paste the private channel ID into the `CHANNEL_INVITE_LINK` variable.
4. Set the `DOWNLOAD_PATH` variable to the desired path where you want the downloaded files to be saved.
5. Run the script and wait for it to start listening for new file messages in the private channel.
6. Any new file, video, or photo message in the private channel will be forwarded to your saved messages and downloaded to the specified download path.

## Configuration

To use the script, you need to provide your Telegram API credentials and set up the desired channel to forward messages from. Open the script and modify the following variables:

- `API_ID`: Your Telegram API ID
- `API_HASH`: Your Telegram API hash
- `SESSION_NAME`: The name of the session (e.g., 'my_session')
- `CHANNEL_INVITE_LINK`: The invite link of the channel you want to forward messages from
- `DOWNLOAD_PATH`: The path where downloaded files will be saved

## Usage

1. Make sure you have set up the configuration variables correctly.
2. The script will create a download folder if it doesn't exist.
3. It will connect to the Telegram API, get the channel ID from the invite link, and start listening for new messages in the channel.
4. Whenever a message, file or photo message is received, it will be forwarded to your saved messages and downloaded to the specified download folder.
5. If the downloaded file is a compressed file (.zip, .7z, or .rar), it will be extracted to a new folder with the same name as the compressed file.
6. The original compressed file will be deleted after extraction to save space.

## Customization

The script includes a few functions that you can customize according to your needs:

- `forward_to_saved_messages`: Handles the event when a file or photo message is received. You can customize the forwarding behavior or add additional actions.
- `get_file_name`: Extracts the file name from a document message. You can modify this function to change the file naming convention.
- `is_compressed_file`: Checks if a file is a compressed file. You can modify the list of supported extensions.
- `extract_compressed_file`: Extracts a compressed file. You can customize the extraction logic or add support for other compression formats.
- `download_file`: Downloads a file message. You can customize the download path or add additional actions.
- `download_photo`: Downloads a photo message. You can customize the download path or add additional actions.
- `event_listener`: The main event listener function. You can modify this function to change the event handling behavior or add additional event handlers.

Feel free to customize the script to fit your specific use case.

## License

This code is released under the MIT License.

You are free to use, modify, and distribute this code for any purpose, commercial or non-commercial, as long as you give proper credit to me.