# ffmpeg

## Contents

- [Convert a Video](#convert-a-video)
- [mkvmerge](#mkvmerge)

## Convert a Video
```
ffpeg -i <input> <output>
```

**Input or Output could be:**
- `.avi`
- `.mp4`
- `.mkv`
- [others]

#### Select Video Codecs
`-vcodec <codec>` or `-c:v <codec>`

**Codecs**

- `mpeg4` MPEG-4
- `libx264` H264
- `libx265` H265
- [others]

#### Select Video Codecs
`-acodec <codec>` or `-c:a <codec>`

**Codecs**

- `libmp3lame` mp3
- `libfdk_aac` AAC
- [others]

#### Select Subtitle Codecs
`-scodec <codec>` or `-c:s <codec>`

**Codecs**

- `ass`
- `srt`
- [others]

#### Multiprocessing
`-threads <n-threads>`

#### Resize Video or Image
`-vf scale=<wight>:<height>`


## mkvmerge

This script is useful to add subtitles to a video:

```bash
mkdir sub

for file in *.mkv
do
  mkvmerge -o "sub/$file" \
  --default-track 0:no --language 0:eng "${file%.*}.en.srt" \
  --default-track 0:no --language 0:ita "${file%.*}.it.srt" \
  --default-track 1 "$file"
done
```
