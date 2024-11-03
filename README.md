
---

# Google OAuth Authentication with Passport.js

This is a simple Express application that uses Google OAuth 2.0 for authentication via Passport.js. It allows users to log in with their Google account, view a personalized profile page, and log out.

## Features

- Google OAuth 2.0 authentication with Passport.js
- Session-based authentication
- Displays a personalized greeting on the profile page
- Simple login and logout functionality

## Prerequisites

To run this project, you'll need:

- [Node.js](https://nodejs.org/) (version 12 or higher)
- A Google Cloud project with OAuth credentials
- A `.env` file to securely manage sensitive information

## Setup Instructions

### Step 1: Google OAuth Credentials

1. Go to the [Google Cloud Console](https://console.cloud.google.com/).
2. Create a new project or select an existing one.
3. Go to **Credentials** in the **APIs & Services** section.
4. Click **Create Credentials** and select **OAuth 2.0 Client IDs**.
5. Configure the consent screen and add `http://localhost:3000/auth/google/callback` as the redirect URI.
6. Note your **Client ID** and **Client Secret** – you’ll need them in the `.env` file.

### Step 2: Clone the Repository

```bash
git clone https://github.com/sahil352005/google-oauth-2.0.git
cd google-oauth-2.0
```

### Step 3: Install Dependencies

Run the following command to install the necessary dependencies:

```bash
npm install
```

### Step 4: Configure Environment Variables

Create a `.env` file in the root directory of the project and add your Google OAuth credentials:

```plaintext
GOOGLE_CLIENT_ID=your-client-id
GOOGLE_CLIENT_SECRET=your-client-secret
```

### Step 5: Run the Server

Start the server with the following command:

```bash
npm start
```

The server should now be running at `http://localhost:3000`.

## Routes

- **`/`** - Home page with a "Login with Google" link.
- **`/auth/google`** - Initiates Google authentication.
- **`/auth/google/callback`** - Callback URL after Google authentication.
- **`/profile`** - Displays the user’s Google display name (only accessible when logged in).
- **`/logout`** - Logs the user out and redirects to the home page.

## How It Works

1. When you navigate to the home page, click the "Login with Google" link.
2. Google will ask for your permission to share your profile information.
3. After granting permission, you’ll be redirected to the `/profile` page, where you’ll see a welcome message with your Google display name.
4. Use the `/logout` route to end the session and return to the home page.

## Troubleshooting

- Make sure the **Google Client ID** and **Client Secret** in the `.env` file are correct.
- Ensure that **http://localhost:3000/auth/google/callback** is added as an authorized redirect URI in your Google Cloud project.
- If you encounter an issue with `req.logout()`, ensure that you’re using Passport version compatible with the session handling method used.

## License

This project is open-source and available under the MIT License.

---

This README provides all essential information for users to understand and set up Google OAuth in this application.
