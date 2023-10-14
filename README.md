# Spotify Clone Application

This repository contains a Spotify clone built using React. The application interfaces with the Spotify API to allow users to browse, play, and manage their Spotify library. It's a great demonstration of how to interact with a third-party API, manage state, and build a modern, responsive UI with React.

## Setup Instructions

1. **Clone this repository** to your local machine.

   ```bash
   git clone https://github.com/jeetpal1/spotify-clone.git
   cd spotify-clone
   ```

2. **Install the required dependencies**.

   ```bash
   npm install
   ```

3. **Update the `src/spotify.js` file** with your Spotify application credentials.

   ```javascript
   // src/config.js
   export const authEndpoint = "https://accounts.spotify.com/authorize";
   const clientId = "your-client-id-here";
   const redirectUri = "http://localhost:3000/";
   const scopes = [
     "user-read-currently-playing",
     "user-read-recently-played",
     "user-read-playback-state",
     "user-top-read",
     "user-modify-playback-state",
   ];
   export const accessUrl = `${authEndpoint}?client_id=${clientId}&redirect_uri=${redirectUri}&scope=${scopes.join(
     "%20"
   )}&response_type=token&show_dialog=true`;
   ```

4. **Run the application locally**.
   ```bash
   npm start
   ```

## Cautionary Notes

- **Credential Safety**: Be cautious when deploying this application on the internet as this is a client-side application and there is no server-side rendering involved. Your Spotify credentials may be revealed in calls from the browser's network section.
- **Updating Credentials**: Ensure to update the `src/spotify.js` file with your Spotify credentials to be able to interact with the Spotify API successfully.
- **Deployment**: It is advisable to add server-side rendering or use serverless functions to handle authentication securely if you decide to deploy this application in a production environment.
