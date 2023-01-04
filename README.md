# WhisperAI Docker

This is a Dockerfile for building Whipser AI image. Whisper is a speech recognition model by OpenApi. You can read more about 
it at their official [Github page](https://github.com/openai/whisper). I created this Dockerfile because there is no official docker image. 
Other means of creating a docker image involve creating a Dockerfile with a lot of dependencies. In contrast, using this Dockerfile should be
straightforward.

## How to Build
Clone this repo and from the root of it, run 
```
docker build -t whisper-ai .
```
Once built, the total image size will be about 6.5 GB.

### Basic Usages
There is no entry point set (you can change this by running the entrypoint command) so you must invoke the whisper cli like so

```
docker run whisper-ai whisper sample.mp3
```

Assuming you have an audio file named ```sample.mp3``` where you are running the docker command from, it should output the speech-to-text transcription to the console. You can redirect it to a file by 
giving the ```---output_dir``` flag with a file name.