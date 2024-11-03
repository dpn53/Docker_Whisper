https://github.com/openai/whisper?tab=readme-ov-file

### Note: The connection between the host machine and container is through the volume mapping (-i argument). 

### From Whisper's github

**Usage from within the container**
`whisper audio.mp3 --model turbo` (from /bin/bash)

### Usage from host

#### Build docker image
$docker_container_tag = "whisper"
docker build -t $docker_container_tag .

#### Set variables 
**Name of host folder with audio file**
$host_path = "."
**Name of folder within the container**
$container_path = "/workspace"
**Name of audio file within the container**
$audio_filename = "12_Efficiency.mp3"
**Name of file to capture the transcription**
$transcription = "$($audio_filename).txt"

**Volume mount needs $() around variable name because of : between host:container variables**
$volume_mapping = "$($host_path):$($container_path)"

docker run --rm -v $volume_mapping -t $docker_container_tag whisper "$container_path/$audio_filename" --language English --model turbo > $transcription
