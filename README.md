# SecureShare — Browser Permission Abuse Awareness Demo

SecureShare is the repository name for a browser-based cyber-awareness proof of concept. Despite the name, **the current code is not a secure file-sharing application**. The page imitates a permission-gated portal and includes invasive client-side collection behavior.

## What the source demonstrates

The current implementation includes behavior related to:
- Requesting browser access to camera, location, and clipboard APIs.
- Capturing keystrokes and collecting device/browser fingerprinting signals.
- Capturing camera frames and collecting location or clipboard information after access.
- Sending collected information to an external Telegram bot endpoint.
- Redirecting the user to an unrelated destination.

These behaviors can compromise privacy and should be treated as a high-risk demonstration, not a deployable product.

## Safety and handling

- Do not deploy this page publicly or use it against unsuspecting users.
- Inspect and test only in an isolated lab with explicit consent and systems you control.
- Do not grant the page real camera, location, or clipboard permissions on a device containing sensitive data.
- If a real bot token has ever been committed to this repository, revoke/rotate it immediately with the bot provider and check repository history. Removing a token from the latest file does not invalidate the exposed credential.
- Do not reuse this implementation as a real login, sharing, or permission-consent flow.

## Inspect the source

The primary page is `index.html`. Read the JavaScript and network requests before opening it in a browser. Avoid serving it from a trusted origin or with access to sensitive accounts.

## Educational objectives

This project can be used to discuss:
- Permission fatigue and deceptive UI patterns.
- Why browser permission grants should be contextual and minimal.
- Client-side telemetry and exfiltration risks.
- The importance of reviewing network destinations and third-party requests.
- How to build transparent, consent-based browser experiences.

## Safer design direction

A legitimate sharing product should explain what is shared, request only necessary permissions, avoid collecting keystrokes or unrelated device data, never send secrets to a chat bot, and provide clear cancellation and revocation paths.

## Maintainer

[Naman Kumar Sonker](https://github.com/nksdev)

## License

See [LICENSE](LICENSE).
