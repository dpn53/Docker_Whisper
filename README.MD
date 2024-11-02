https://github.com/openai/whisper?tab=readme-ov-file

### From Whisper's github

**Usage**

`whisper audio.mp3 --model turbo` (from /bin/bash)

### Real world example
`docker run --rm -v ".:/workspace" e30d278f1ddd whisper /workspace/12_Efficiency.mp3 --language English --model turbo`

**where**
- ".:/workspace" mounts the current working directory to the container's workspace folder
- e30d278f1ddd is the image id and
- 12_Efficiency.mp3 is the audio file in the current working directory
