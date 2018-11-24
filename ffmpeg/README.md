# ffmpeg

## Convert a Video
```
$ ffpeg -i <input> <output>
```

**Input or Output could be:**
- `.avi`
- `.mp4`
- `.mkv`
- [others]

### Select Video Codecs
`-vcodec <codec>` or `-c:v <codec>`

**Codecs**

- `mpeg4` MPEG-4
- `libx264` H264
- `libx265` H265
- [others]

### Select Video Codecs
`-acodec <codec>` or `-c:a <codec>`

**Codecs**

- `libmp3lame` mp3
- `libfdk_aac` AAC
- [others]

### Select Subtitle Codecs
`-scodec <codec>` or `-c:s <codec>`

**Codecs**

- `ass`
- `srt`
- [others]

### Multiprocessing
`-threads <n-threads>`

### Resize Video or Image
`-vf scale=<wight>:<height>`
