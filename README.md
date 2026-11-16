# MYFLIX Live TV — Android / Android TV starter project

This is a WebView wrapper for the ISP-hosted MYFLIX portal at `http://10.20.80.22/`.
It does not extract or redistribute streams; playback remains on the ISP website.

## Important network requirement
The phone / Android TV must be connected to the ISP network that can open `http://10.20.80.22/`. This private IP will not normally work over mobile data or another internet connection.

## Build APK
1. Install Android Studio (current stable) with Android SDK Platform 35.
2. Open this `myflix-android` folder in Android Studio.
3. Allow Gradle sync to finish.
4. Select **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
5. Android Studio will show the generated APK location (normally `app/build/outputs/apk/debug/app-debug.apk`).

## Remote keys
- D-pad Up / Down: move through detected channel cards and select the previous / next one.
- OK / Enter: activate the currently highlighted card.
- Left / Right: volume down / up when a HTML5 video element is exposed by the page.
- Back: browser back navigation.

## Notes / limitations
- The portal's actual DOM and video implementation cannot be inspected from outside the ISP's private network. The remote script therefore detects visible channel-card-like controls heuristically. It may need a small selector adjustment after testing on your ISP portal.
- If the site requires a browser login/session, sign in inside the app if prompted. WebView stores the session locally.
- Some protected players may block WebView playback or hardware decoding; if that happens, the ISP portal must explicitly support Android WebView or provide an authorized stream/player endpoint.
- The app starts at the portal home page. Navigate to Live TV if the portal does not open it automatically.
