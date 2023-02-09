# Image Generation

## Prerequisites

```
pip install diffusers transformers accelerate scipy safetensors torch xformers
```

## Scripts

 * `./generate "prompt1" "prompt2" ... X [--no-cooldown] [--diffuser <diffuser_name>]`

    This can take any number of prompts, make sure each prompt is surrounded by "".  In place of X can be any number, this is how many images to generate per prompt. 
    
    The `--no-cooldown` option is used to stop the script from checking the gpu temperature before generating. Without this flag the script will pause execution if the temperature is over 75ºC after generating an image. It will wait until the temperature is at 65ºC before resuming generation.

    You can specify a diffuser with `--diffuser <diffuser_name>` where `diffuser_name` can be:
    * `sd2` - stabilityai/stable-diffusion-2-1
    * `er` - nitrosocke/elden-ring-diffusion
    * `epic` - johnslegers/epic-diffusion-v1.1
    * `dream1` - dreamlike-art/dreamlike-diffusion-1.0
    * `dream2` - dreamlike-art/dreamlike-photoreal-2.0
    * `protogen` - darkstorm2150/Protogen_Infinity_Official_Release
    * `nitro` - nitrosocke/Nitro-Diffusion

    When not provided the diffuser defaults to protogen.

* `./temp` - displays the current gpu temperature