# Narrata — Support

Narrata is an audiobook player for [Audiobookshelf](https://www.audiobookshelf.org) servers that
you host yourself. It is an independent app and is not affiliated with or endorsed by the
Audiobookshelf project.

## Before you start

**You need your own Audiobookshelf server.** Narrata is a client, not a store or a library — it
plays audiobooks from a server you already run. If you don't have one, there is nothing for the
app to connect to.

Requirements:

- iOS 26 or later
- An Audiobookshelf server reachable from your device
- Server v2.26 or newer recommended. Older servers work, falling back to the legacy permanent
  token instead of the rotating-token model.

## Getting connected

1. Open Narrata and enter your server address — for example `https://books.example.com`, or
   `http://192.168.1.50:13378` on your local network. If you leave off the scheme, `https://` is
   assumed.
2. Sign in with your Audiobookshelf username and password, or use **Sign in with OIDC** if your
   server has SSO configured.
3. Pick a library and start listening.

## Common problems

**"That doesn't look like a valid http(s) server address."**
Narrata accepts only `http://` and `https://` addresses. Check for typos, and include the port
if your server uses a non-standard one.

**Can't reach a server on my home network from outside the house.**
Narrata connects directly to the address you give it and does not proxy through anything. A LAN
address only works while you are on that network. For access from elsewhere you need a VPN back
to your network, or your server exposed over HTTPS with a public hostname.

**Plain-HTTP address won't connect.**
iOS restricts unencrypted connections. Narrata permits them for local-network addresses only.
Anything reachable over the internet needs HTTPS.

**Login worked before and now fails.**
Access tokens expire and refresh tokens rotate. If the server was rebuilt, its sessions were
reset, or your password changed, sign out and sign in again.

**Downloads stall or don't finish.**
Transfers run on a background session and continue when the app is closed, but iOS schedules
them at its own discretion — low battery, Low Power Mode, and poor connectivity all delay them.
Downloads resume on their own; opening the app and staying on the Downloads screen usually
prompts iOS to get on with it.

**Progress from offline listening didn't reach the server.**
Offline progress is queued and synced on reconnect. Open the app while connected and give it a
moment. Progress is preserved on the device until the sync succeeds — it isn't lost.

**The Continue Listening widget is stuck on an old book.**
The widget renders from a snapshot the app writes. Open the app and play something to refresh
it. iOS also budgets widget refreshes, so it can lag behind briefly.

**Playback stops when I lock the screen.**
Narrata plays in the background and shows lock screen controls. If audio stops, check that
another app didn't take over the audio session, and that Narrata isn't restricted under
**Settings › General › Background App Refresh**.

## Reporting a bug

Please include:

- What you did and what happened instead
- Your iOS version and device model
- Your Audiobookshelf server version
- Whether the book was streaming or downloaded

## Privacy

Narrata collects nothing. Your credentials stay in the iOS Keychain and your listening data goes
only to your own server. Full detail in the [privacy policy](privacy.md).

## Contact

**support@leonfamily.net**
