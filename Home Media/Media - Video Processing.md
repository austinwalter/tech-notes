## Video Processing
My current method (which admittedly you will only find "friendly" if you're comfortable with the command line):

#### Prerequisites
* MakeMKV
* Handbrake CLI
* [The `video_transcoding` Ruby Gem](https://github.com/donmelton/video_transcoding)
* `mediainfo` command.

#### Method
1. Rip the disc using MakeMKV and `cd` to the directory containing the output file(s) you want to encode. Delete any files you don't want to encode.

2. `transcode-video --scan title00.mkv` to check if there's any additional audio or subtitle tracks you want to include. Also detects any obvious combing/interlacing.

3. `mediainfo title00.mkv` to double-check that the video really isn't interlaced. Might want to skip through it in a media player, too.

4. `mkdir processed && cd processed && transcode-video ../*.mkv`. You might need to add `--filter deinterlace` or `--add-audio ...` or `--add-subtitle ...` here, accordingly (see extensive README file in the above link).

Very occasionally I find that the `--scan` step doesn't detect a language track at all when there is definitely one present, especially when the audio codec is "pcm_s16le". When this happens I use the following command to quickly convert the audio to FLAC or some other lossless audio format that I know it'll pick up, and then run the --scan again on the new file:

```
ffmpeg -i title00.mkv -c:v copy -c:a flac title00-flac.mkv
```


https://unix.stackexchange.com/questions/284005/convert-image-based-subtitle-to-text-based-subtitle-inside-mkv-file

https://github.com/ruediger/VobSub2SRT
https://github.com/mjuhasz/BDSup2Sub

MKVToolNix

https://askubuntu.com/questions/452268/extract-subtitle-from-mkv-files
https://stackoverflow.com/questions/29881826/bash-script-to-extract-information-from-a-block-of-text-spanning-multiple-lines
https://stackoverflow.com/questions/42899989/parse-the-output-of-mkvinfo-in-bash-with-gawk
https://www.reddit.com/r/PleX/comments/9a8y8s/batch_extract_subtitles_from_mkv_files/

#### Related

[[Media - Create Server Image]]
