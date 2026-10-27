NEEDLE — MIDNIGHT VINYL (PWA package)

WHAT THIS IS
A web app package designed to be hosted over HTTPS and added to the iPad Home Screen. It opens in an app-like standalone window.

WHY IT CANNOT BE "ONE CLICK" YET
Spotify requires an OAuth app Client ID and an exact registered redirect URI for account/library access. Spotify does not provide a universal button that lets an arbitrary third-party app access a user's library without an app registration and consent. This package uses PKCE and does not need a client secret in the browser.

SETUP (ONE-TIME)
1. Host this folder on an HTTPS static host (for example, a static site host you control).
2. Create a Spotify developer app at https://developer.spotify.com/dashboard/
3. In the Spotify app settings, add the exact hosted URL of index.html as an allowed Redirect URI.
4. Edit config.js and set:
   clientId: "YOUR_CLIENT_ID",
   redirectUri: "https://YOUR-HOSTED-SITE/index.html"
   The redirect URI must exactly match the one registered with Spotify.
5. Open the hosted page on the iPad in Safari, then Share > Add to Home Screen.
6. Tap Connect Spotify and approve the requested permissions. Afterwards, you can browse playlists from the app.

NOTES / LIMITATIONS
- This package is not a signed native iOS .ipa. Building and installing a native iPad app requires an Xcode build/signing workflow and Apple developer provisioning.
- Spotify playback is provided through Spotify's official embed. Some tracks/playback actions may require Spotify login or Premium and are subject to Spotify's policies and API availability.
- The animated bars are decorative, not audio-reactive.
- Never place a client secret in config.js or other browser code.


NEEDLE v3 update: immersive full-screen vinyl scene with album sleeve left, spinning record and tonearm right, and Spotify embed controls at the bottom. Select a playlist/album/track to enter the vinyl scene. Spotify embeds are cross-origin, so the page cannot directly detect taps inside Spotify’s own Play button; the vinyl scene opens when the record is selected, and Spotify playback is started using the embedded controls.
