Firstly, open your terminal, navigate to the project directory, and run:
'pip install -r requirements.txt'. 
Then, create a folder called '.streamlit', where inside it, create a file named 'secrets.toml'.
Run the file. Paste the following configuration inside the triple backticks to be able to access the prior posts:
```
[supabase]
url = "https://duombglwgussqtosxqtd.supabase.co"
# IMPORTANT: Remove the space after 'sb_secret_' when pasting into your secrets.toml
key = "sb_secret_ WgMGEUE2TQwsNv74U_pJhQ_Cx2x4_y_"
# Replace these with your actual keys
GOOGLE_API_KEY = "your_google_gemini_api_key_here"
COOKIE_SIGNING_KEY = "your_cookie_signing_key_here"
```
You also need 2 extra keys, GOOGLE_API_KEY and COOKIE_SIGNING_KEY.
For GOOGLE_API_KEY, it is used to access the AI features in the app, the AI Study Buddy and the AI Autotagging. 
1. Go to Google AI Studio, https://aistudio.google.com/app/apikey.
2. Sign in with your Google account.
3. Click on ""Create API key"".
4. Copy the generated key and replace `your_google_gemini_api_key_here` in your `secrets.toml` file.
For COOKIE_SIGNING_KEY, it is a secret string used to securely sign session cookies. It should be a long, random, and unguessable string.
- You can generate a strong key quickly in your terminal by running: `python3 -c ""import secrets; print(secrets.token_hex(32))""`
- Copy the generated string and replace `your_cookie_signing_key_here` in your `secrets.toml` file.

Once your dependencies are installed and your secrets are configured, you can start the application! Run the following command in your terminal:

`streamlit run app.py`