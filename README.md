# Kairos audio pitch

A simple audio player with repeat enabled by default, a speed selector and a restart button. No build or installation is needed.

The player has a full-width timeline with a large drag handle, elapsed and total time, a prominent play/pause button, and 10-second back/forward buttons. On small screens the timeline has a 60px touch area and a 36px handle. Drag or tap it to move to a particular time; keyboard arrow keys also adjust playback position. The browser's native player remains available when JavaScript is disabled.

Open [index.html](index.html) in your browser and press Play. Keep `pitch.mp3` beside `index.html` when moving or downloading the player.

## Live player and website sync

The same page is also hosted at **https://kairos-community.vercel.app/audio-ptch.html** on the existing Kairos Vercel project. This repository remains the source for both copies.

After any change to `index.html` or `pitch.mp3`, run `npm run audio:sync` from the sibling `../website/` repository. This copies both files byte for byte, with checksums in `website/audio-pitch/manifest.json`. Commit the changes in both repositories and push the website to update Vercel. Local website builds also sync automatically; Vercel builds verify the committed copies. Do not edit the website's public copies separately.

## Listen while using your phone

Start playback, then switch apps or lock the screen while leaving the browser tab open. The player uses native audio and native looping, and adds play, pause and seek controls to the lock screen or media notification where supported. It also requests the playback audio-session mode when the browser provides it.

Closing the tab or quitting the browser ends playback. Background playback still depends on your phone and browser; the page cannot override operating-system restrictions or interruptions. The controls and looping have been checked in desktop Chrome, but a physical phone/locked-screen test is still needed. See the [Media Session guide](https://web.dev/articles/media-session).

## Update the voice note

1. Replace `pitch.mp3` with the latest MP3 recording, keeping the same filename.
2. Reload `index.html` in your browser.
3. Commit the updated recording in VS Code and push it to your private repository.

Git retains earlier committed recordings in the repository history. The page needs no rebuilding when the recording changes.

## Publish the repository from VS Code

1. Open the Command Palette with `Cmd+Shift+P`.
2. Run **Publish to GitHub**.
3. Use the name **kairos-audio-pitch** and choose **private**.

See the [VS Code publishing instructions](https://code.visualstudio.com/docs/sourcecontrol/repos-remotes#publish-to-github). A private repository restricts access to the stored files. Publishing the repository does not itself host a website; a hosted website's access settings are separate. See [GitHub repository visibility](https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories#about-repository-visibility) and [GitHub Pages visibility](https://docs.github.com/en/enterprise-cloud@latest/pages/getting-started-with-github-pages/changing-the-visibility-of-your-github-pages-site).
