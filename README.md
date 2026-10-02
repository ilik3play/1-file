# 1-file

## Mashup Studio

`index.html` is a self-contained browser app for making mashups. You can put the vocals from one song over the beat from another, or combine sections from several songs. It needs no build and no install: open the file in Chrome or Edge.

### How songs get in

- **Your own files.** Drag audio files (MP3, WAV, M4A, FLAC, OGG) onto the **Add songs** box, or click it to choose files. Files are read directly by your browser and are **never uploaded**.
- **iTunes.** Type a song or artist into the search box and press **Search iTunes**, then **+ Add** on a result. Apple only makes **30-second preview clips** available, so that's what gets added; for the full track, use a file you own. Searches go to Apple's public iTunes Search API, and the store region follows your browser's language setting. Previews are AAC audio, which Chrome, Edge and Safari can decode.

Streaming services such as Spotify don't give apps access to the raw audio, so they can't be used as a source.

### Making a mashup

1. **Add songs.** Each song's tempo (BPM), beat grid and key are detected automatically.
2. **Split vocals & music** (optional). An AI model (Meta's Demucs, via [`demucs-web`](https://github.com/timcsy/demucs-web)) runs in your browser and separates the singing from the instruments. The model downloads once, about 170 MB, and is then kept in the browser's cache. It uses your graphics card through WebGPU when available; if the graphics card fails or takes more than a minute to start, it switches to the processor, which is slower (several minutes per song).
3. **Pick lines by lyric** (optional). Each song card looks up time-stamped lyrics from [LRCLIB](https://lrclib.net), a free lyrics database; edit the search box if it finds the wrong song. Click a line to hear it, and press **+** to add it to the mashup. Lines are cut on the song's beats, use the vocals if the song has been split, and are placed one after another on Vocals 1, on the same beat of the bar as in their own song, so you can build a verse from lines of different songs. If the lyrics run early or late against your file, adjust **Lyrics timing**.
4. **Pick a section.** Choose the Full song, Vocals or Instrumental tab, then drag across the waveform. Selections snap to bars.
5. **+ Beat** puts the section on the Beat lane. **+ Vocals** puts it on a Vocals lane at the playhead.
6. **Arrange.** Drag sections to move them, drag their edges to trim them, and use Duplicate or Delete. Each lane has mute, solo and volume controls.
7. **Tempo and key.** Every section is time-stretched to the mashup tempo without changing its pitch. Vocal sections are shifted to the beat's key automatically, and **Key shift** / **Match key** let you adjust that.
8. **Export WAV** downloads the finished mashup.

Keyboard: `Space` plays or pauses, `Delete` removes the selected section, and `Ctrl/⌘+D` duplicates it.
