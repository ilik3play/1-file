# 1-file

## SongSync

`index.html` is a self-contained browser app that syncs two songs together. It needs no build and no install: open the file in a browser.

1. Load a song into deck **A** and another into deck **B** (drag and drop, or click).
2. Each song's tempo (BPM) and beat grid are detected automatically. Both songs then play at a shared **Mix BPM** with their beats aligned.
3. Fine-tune the result:
   - **BPM** per deck: type a value, use ÷2 / ×2, or tap along.
   - **B enters**: choose which beat of song A song B starts on. You can move it by a beat or a bar (4 beats).
   - **Nudge B**: shift song B by milliseconds. The ← / → keys move it by 5 ms.
   - **Mark beat**: during playback, press exactly on a beat to correct that song's beat grid.
4. Use the crossfader and volume sliders to balance the two songs, then **Export mix** to download a WAV.

The beat alignment view shows the drum hits of both songs around the playhead. When the songs are in sync, the peaks line up.

Note: tempo matching changes playback speed, so pitch shifts along with it, as on a turntable.
