# Milan’s RedGifs Video Downloader

A lightweight Chrome extension for downloading videos directly from RedGIFs.

**Milan’s RedGifs Video Downloader** adds a download button to supported RedGIFs video players, automatically prefers the HD version when available, and saves the requested video through Chrome’s normal **Save As** dialog.

No external downloader website. No conversion service. No account. No subscription. No ads.

> This extension is intended for personal use. Respect the original creators and do not republish, redistribute, or present downloaded content as your own without permission.


![Milan’s RedGifs Video Downloader](red-gif-downloader.png)


## What It Does

- Adds a download button directly to supported RedGIFs videos
- Automatically prefers the HD version when RedGIFs provides one
- Falls back to SD when HD is unavailable
- Downloads directly from RedGIFs media infrastructure
- Uses Chrome’s normal **Save As** dialog
- Works with regular RedGIFs video players
- Supports the expanded/fullscreen viewer
- Remembers whether download buttons are enabled
- Includes a small local Error Log for troubleshooting
- Does not use analytics, advertising trackers, or telemetry

The extension is intentionally focused. It downloads RedGIFs videos and avoids turning a simple job into a small software ecosystem.

## How It Works

When you browse RedGIFs, the extension detects supported video players and adds its own download control.

When you click the button:

1. The extension identifies the RedGIFs clip.
2. It requests the media information needed for that clip from RedGIFs.
3. It prefers the HD video URL when one is available.
4. If HD is unavailable, it falls back to the available SD version.
5. Chrome opens its normal **Save As** dialog so you can choose where to store the file.

The requested video is downloaded from RedGIFs infrastructure. It is not uploaded to my server and is not routed through a third-party downloader or conversion service.

If API resolution is temporarily unavailable, the extension can use a valid RedGIFs-hosted media source already available to the player as a fallback.

## Simple Settings

The extension popup contains one main setting:

### Download buttons

Enabled by default.

Turn it off and the extension removes its download controls from RedGIFs. Turn it back on and they return.

The preference is stored locally using Chrome extension storage.

## Privacy

Milan’s RedGifs Video Downloader does not use:

- Analytics
- Advertising trackers
- Usage tracking
- Telemetry
- User accounts
- Registration
- External downloader services

The extension communicates with RedGIFs only as needed to identify and download the video requested by the user.

A temporary RedGIFs API token may be obtained directly from RedGIFs when required. It is used only for communication with RedGIFs and is not sent to the developer.

The extension does not maintain a history of downloaded videos.

For the full privacy details, see the privacy policy on the IT SUCKS! website:

[Privacy Policy for Milan’s RedGifs Video Downloader](https://www.itsucks.fyi/privacy-policy-milans-redgifs-video-downloader/)

## Error Log

RedGIFs is a dynamic website and may change its player, API, or page structure.

For troubleshooting, the extension includes a small local **Error Log**. If a download fails, open the extension popup and select **Error log**.

The log is temporary, limited in size, and is not automatically transmitted anywhere.

If you report a problem, copying the relevant error message makes troubleshooting considerably easier than simply writing:

> It doesn’t work.

## Installation

### Chrome Web Store

The extension is intended for distribution through the Chrome Web Store.

### Manual installation for development

1. Download or clone this repository.
2. Open `chrome://extensions/` in Chrome.
3. Enable **Developer mode**.
4. Click **Load unpacked**.
5. Select the extension directory.

Manual installation is mainly useful for development and testing.

## Responsible Use

Saving a file does not make it yours.

Use downloaded content for personal use and respect the original creator’s rights. Do not repost downloaded videos on social media, redistribute them, or present somebody else’s work as your own unless you have the necessary permission.

## Article and Support

The full article about the extension, including additional background, usage information, privacy notes, and support comments, is available here:

[Why I Made Milan’s RedGifs Video Downloader](https://www.itsucks.fyi/milans-redgifs-video-downloader/)

If you run into a problem, leave a comment below the article and include any relevant information from the extension’s Error Log.

## Changelog

Technical development history for **Video Downloader for X**.

The extension began as **Private X Video Downloader**, was later renamed **Simple X Video Downloader**, and is now **Video Downloader for X**.

This changelog intentionally focuses on meaningful technical changes, compatibility improvements, privacy-related changes, and feature development. Minor visual adjustments, icon revisions, spacing changes, wording tweaks, and other cosmetic work are omitted.

## 1.5.6 — September 29, 2026

Reliability and maintenance release.

- Prevented settings controls from being used before stored preferences finish loading.
- Added safer handling for overlapping preference writes.
- Restores the previous setting state if a save operation fails.
- Simplified duplicated video/image control code.
- Consolidated shared download-button construction and styling.
- Kept the existing video-resolution and image-download behavior unchanged.

### October 6, 2026 — Public naming update

- Renamed the extension from **Simple X Video Downloader** to **Video Downloader for X**.
- Kept version **1.5.6**.
- No permissions, download logic, settings, or feature behavior changed as part of the rename.

## 1.5.5 — August 21, 2026

Major compatibility and reliability hardening.

- Improved behavior during long X browsing sessions.
- Capped remembered GraphQL request URLs to avoid unnecessary growth.
- Improved rescanning when X dynamically changes `src`, `srcset`, inline styles, or media-player DOM structures.
- Prevented image download controls from attaching to video poster or cover elements.
- Improved detection of lightbox images and media without the expected wrapper structure.
- Strengthened original-image URL normalization.
- Added JPEG/PNG probing when WebP or AVIF previews do not map cleanly to an original asset.
- Added safer MIME-type and response-content validation for media probes.
- Improved Unicode-safe filename handling.
- Added support for additional retweet and `TweetDetail` metadata paths.
- Added timeouts and stronger fallback behavior for X metadata requests.
- Improved error reporting for rate limits, timeouts, interrupted downloads, and non-media responses.
- Added rescanning after bfcache restoration or tab suspension.
- Expanded page matching to X/Twitter subdomains.
- Reduced Chrome Web Store host permissions to the required X and `twimg.com` endpoints.

## 1.5.4 — August 21, 2026

Reworked optional image downloading while preserving the stable video engine.

- Kept the proven **1.3.7 video resolver** as the video-download base.
- Reintroduced the optional **Download images** feature.
- Changed image detection to use visible X photo media as the primary source of truth.
- Rejected video covers, profile images, card artwork, and other non-photo imagery.
- Added image discovery through standard image sources, `srcset`, CSS backgrounds, and lightbox media.
- Rewrote X preview URLs toward original-size assets where possible.
- Added format probing for difficult WebP and AVIF preview cases.
- Improved filename handling for emoji and other multi-codepoint characters.
- Improved fallback behavior so successful recovery paths do not create misleading Error Log entries.

## 1.5.3 — August 21, 2026

Temporary stability-focused revision.

- Returned video downloading to the stable **1.3.7 video engine** while the image-download implementation was being redesigned.
- Removed the experimental image-download path from this build.
- Preserved the existing video-download and local diagnostic behavior.

## 1.5.2 — August 20, 2026

Image and filename reliability update.

- Expanded discovery of X photo URLs from rendered page media.
- Improved handling when X rearranges photo markup dynamically.
- Strengthened original-image URL handling.
- Added safer fallback filenames for both videos and images.
- Improved handling of invalid filenames reported by Chrome.

## 1.4.0–1.4.3 — August 19–20, 2026

Image downloading and local settings were added.

### 1.4.0

- Added optional image downloading.
- Added independent **Download videos** and **Download images** settings.
- Added local preference storage using `chrome.storage.local`.
- Kept image downloading disabled by default.
- Added original-size image handling and image-specific filenames.

### 1.4.1

- Refactored shared video/image button creation.
- Improved fallback photo discovery.
- Added stricter validation for X post IDs used by the syndication fallback.
- Added the extension version to diagnostic output.

### 1.4.2–1.4.3

- Clarified and cleaned up the implementation around X session metadata.
- Documented the use of the page-visible `ct0` CSRF value.
- No significant downloader behavior change.

## 1.3.7 — August 18, 2026

Video resolver compatibility update.

- Improved MP4 recognition using both URL structure and MIME information.
- Improved HLS rejection using both `.m3u8` URLs and HLS MIME types.
- Preserved content-type information from VMAP media entries.
- This version later became the stable video engine reused by the 1.5.x line.

## 1.3.0–1.3.3 — August 17–18, 2026

Reduced dependence on X internals and added local diagnostics.

### 1.3.0

- Replaced active JavaScript bundle parsing with a passive **Resource Timing** fallback.
- Reused X's own observed `TweetResultByRestId` request structure where available.
- Reduced reliance on hardcoded GraphQL operation details.

### 1.3.1

- Added a temporary per-tab **Error Log**.
- Stores a small number of recent failures in content-script memory.
- Records errors only when the complete resolution attempt fails, avoiding noise from successful fallback paths.
- Added popup access to the diagnostic log.

### 1.3.2–1.3.3

- Refined diagnostic behavior and reporting.
- Clarified that diagnostic information is copied manually and is never transmitted automatically.

## 1.2.0–1.2.8 — August 17, 2026

Added the popup and established the first public release identity.

### 1.2.0

- Added the toolbar popup.
- Added privacy information and a link to the project article.
- Kept the popup local, with no analytics, tracking, or external settings service.

### 1.2.6

- Renamed the extension from **Private X Video Downloader** to **Simple X Video Downloader**.

### 1.2.8

- Improved reliability of the injected media control over X's interface.

## 1.1.0–1.1.3 — August 17, 2026

Major hardening of the original video-only downloader.

### 1.1.0

- Added readable filenames based on post text and video resolution.
- Improved reinsertion when X rebuilds video-player DOM nodes.
- Improved GraphQL operation discovery.
- Added quoted-post support to the syndication fallback.
- Made VMAP parsing namespace-safe.
- Set the minimum supported Chrome version to 150.
- Preserved Chrome's normal **Save As** workflow.

### 1.1.1

- Replaced the externally loaded button asset with inline SVG construction.
- Removed the need to expose that asset as a web-accessible resource.
- Improved resilience across extension reloads and updates.

## 1.0.0 — August 17, 2026

Initial release as **Private X Video Downloader**.

- First working Manifest V3 build.
- Added a download control directly to X video players.
- Selected the highest-resolution direct MP4 available from X.
- Used bitrate as a tie-breaker when multiple variants had the same resolution.
- Did not limit downloads to the quality currently being played in the browser.
- Added multiple media-resolution paths, including GraphQL, guest-token, VMAP, and syndication fallbacks.
- Restricted background downloads to X media.
- Used Chrome's normal download system and **Save As** dialog.
- Included no analytics, telemetry, account system, external downloader service, or cloud backend.


## About

Milan’s RedGifs Video Downloader is part of the **IT SUCKS!** project.

[Visit IT SUCKS!](https://www.itsucks.fyi/)

Sometimes you just want to save some stuff on your hard drive.

You don’t need it.

You just want it.

And when that simple option isn’t available?

**It sucks.**
