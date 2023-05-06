Here's a more organized version of the instructions for setting up and running the Telegram Deezer Bot:

1. Clone the repository and make it private.

2. Install the required packages using `pip install -r requirements.txt`.

3. Open the `keys.py` file and add the following:

   ```
   api_id = "<your_telegram_api_id>"
   api_hash = "<your_telegram_api_hash>"
   bot_token = "<your_telegram_bot_token>"
   service_file = "client_secrets.json"  # no need to rename this
   db_url = "<your_mongodb_connection_string>"
   deezer_api = "<your_deezer_api_key>"
   ```

4. Run the bot using `python3 main.py`.

5. For the `db_url`, create an account in MongoDB and assign or create a user in it.

6. For the `service_file`, remove the already present `client_secrets.json`. Then, go to Google Cloud Console, create a service account, and download the service account file in JSON format. Rename the JSON file to `client_secrets.json`, upload it to your repository, and don't forget to add your service account in your shared drive with content manager/manager permissions.

7. For Google Drive support, follow these steps:

   - Create a folder in your Google Drive.
   - Get the folder ID of the created folder by visiting the folder in Google Drive and checking the URL. The folder ID will be the long string of characters after `https://drive.google.com/drive/folders/`.
   - Use the folder ID to set `TEAMDRIVE_ID` in `settings.py`.
   - Get the folder's index link by opening the folder in Google Drive and copying the URL from your browser's address bar. Set `SERVICE_FILE_URL` in `keys.py` to the index link.
   - Set `TRACK_TOKEN` in `keys.py` to the same value as `deezer_api` (i.e., the ARL token).

That's it! You should now be able to run the Telegram Deezer Bot.
