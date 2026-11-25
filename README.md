# Maze Snake Live (starter)

## What is included
- `public/index.html`: portrait Maze Snake game, gold maze, apple, level, gift legend, test commands.
- `server.js`: optional YouTube Live Chat connector using YouTube Data API OAuth.
- Commands: `67` = apple, `999` = color change, `666` = bomb.
- Super Chat: adds apples using a simple ₹10-per-apple style mapping. The displayed currency string comes from YouTube.

## Important limitations
- This is a starter project, not a finished clone of the exact maze in the reference screenshot. The maze is generated procedurally and the visual layout is similar.
- YouTube subscriber names/alerts are not provided as a reliable new-subscriber event by this basic Live Chat API connector. Use a separate supported alert provider or add a manual alert overlay.
- Likes are currently a visual counter placeholder. A real like counter needs a separate YouTube video statistics request and API quota.
- The web page itself does not publish RTMP to YouTube. Use a mobile screen-broadcast app (for example PRISM Live Studio screen mode, if available on your device) to capture the game screen and stream it.
- Keep OAuth secrets private. Never put the Google client secret or refresh token in `index.html`.

## Run on Android
Use a cloud Node.js workspace/deployment in Chrome on Android (a PC is not required):
1. Upload this project ZIP and extract it.
2. Open the Shell/Terminal and run `npm install`, then `npm start`.
3. Open the generated app URL. It should show the game in demo mode.
4. For YouTube chat integration, create a Google Cloud project, enable **YouTube Data API v3**, configure an OAuth consent screen, and create an OAuth Client ID of type **Web application**.
5. Add the exact callback URL of your deployed app plus `/oauth2callback` as an authorized redirect URI.
6. Set these environment variables in your hosting dashboard:
   - `GOOGLE_CLIENT_ID`
   - `GOOGLE_CLIENT_SECRET`
   - `REDIRECT_URI` (exact deployed URL + `/oauth2callback`)
7. Restart the app, open `/auth`, sign in to the YouTube channel that is live, approve read-only access.
8. Return to the game URL and use the Start Live Chat action/API. Tap the **START CHAT** button in the game page; it sends the required POST request. The backend finds your currently active broadcast.
9. In the game page tap **CONNECT YOUTUBE**, approve access, return to the game, then tap **START CHAT**.
10. Start screen broadcasting from the phone and show the game page full-screen.

## Notes
- YouTube must have an active live broadcast and live chat enabled before `/api/start`.
- The backend follows YouTube's `pollingIntervalMillis`; do not poll faster than the API requests.
- Hosting must support a long-running Node process and HTTPS OAuth callback. A static-only host is not enough.
