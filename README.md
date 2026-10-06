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

See [changelog.md](changelog.md) for version history and notable changes.

## About

Milan’s RedGifs Video Downloader is part of the **IT SUCKS!** project.

[Visit IT SUCKS!](https://www.itsucks.fyi/)

Sometimes you just want to save some stuff on your hard drive.

You don’t need it.

You just want it.

And when that simple option isn’t available?

**It sucks.**
