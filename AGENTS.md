# Kairos audio player

This is the canonical source for the standalone player and the copy at
https://kairos-community.vercel.app/audio-ptch.html.

After every player or recording change, also run `npm run audio:sync` from the
sibling `../website/` repository, then verify and commit both repositories.
Do not edit the generated `website/public/audio-ptch.html` or `public/pitch.mp3`
independently. Website builds sync from this folder locally; Vercel verifies
the committed copies without needing access to this separate repository.

Keep the native audio engine, large mobile controls, offline support and
system media controls. Preserve recordings in Git before replacing them.
Do not change repository visibility. The user explicitly authorized the
21 November migration and push; do not infer permission for unrelated work.
