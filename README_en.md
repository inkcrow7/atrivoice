# MoeTTS
Speech synthesis model repo for galgame characters based on Tacotron2 , Hifigan and VITS. The repo is also used to publish precompiled GUI.

[简体中文](README.md)   [English](README_en.md)

## About

Speech synthesis model repo for galgame characters based on Tacotron2, Hifigan and VITS. The repo is also used to publish precompiled GUI.

Reference:

hifi-gan: https://github.com/jik876/hifi-gan

Tacotron2: https://github.com/NVIDIA/tacotron2

VITS:https://github.com/jaywalnut310/vits

## User Agreement

On the basis of the open source agreement please also comply with the following rules.

1. (Important) Do not use this software, the pre-trained models provided by this repository or the speech synthesis results for direct commercial purposes (e.g. QQ bots, direct sales, commercial games, etc.) derivative work is not included.
2. Please comply with the user agreement of the original work and do not create content that will adversely affect the original work.

## Tutorial

### File directory format

If the model does not have a configuration file, you can place it in any directory, if the model has a configuration file, rename it to `config.json` and place it in the same directory as the model

### Inputs

Mostly you need to input phoneme (In Japanese, it stands for the Roman Tones), but the author of the models can decide other input methods. For exmaple, the ATRI model(Tacotron2 version) supports Roman Tones without spaces only and the commas and the periods only.

### custom cleaner and symbols

You can find the `custom` folder in the same level as `moetts.exe`, which contains the text modules for both TTS models.

1. custom cleaners: locate `cleaners.py` and modify the `custom_cleaners` function (the software does not process text by default)
2. Custom symbols: locate `symbols.py` and change the symbols inside to the symbols you need

Note: Different models may be trained with different cleaners and symbols, please modify them if necessary to ensure that the model works well.

### GUI

![User Interface](assets/tacotron2.png)

After opened the software, please choose your model's path and output path. At last, type the text need to be speaked, click on the "合成语音" button, wait for a while, then the software will output the audio to the /{output_path}/outpus.wav

Notes:

 1. Because of the model loading, when generate voice for the first time, it may take a long time. However, the same model won't be reloaded when generate for the next time and will directly generate the voice.
 2. If you change the model, the software will reload it when generate voice next time.
 3. If you have modified cleaners and symbols, you will need to restart the software for them to take effect.
 4. The software supports amd64 only, instead of i386.

About VITS

![vits](assets/vits.png)

1. VITS-Single and VITS-Multi are single speaker model and multi speaker model respectively.
2. the `原角色ID` in VITS-Multi is the ID of the speaker to be synthesized, you need to provide a number, the `目标角色ID` is used as the target speaker id for `voice conversion`.
3. Using `语音迁移`(voice conversion) requires a wav file with a sample rate of 22050.

## Model Downloads

Submit models in this model:

x. Model's name

Description: Model of the character xxx

Input method: 

Download address:

Hifigan's Model download address: Optional

More info: Optional

Model type: 



1. ATRI

   Description:  ATRI - Character's model of *My dear moments* 

   Input method: Roman tone without spaces. Only English comma or period accepted. Choose basic_cleaners for the Cleaners option. For example: `tozendesu.koseinodesukara.`

   Download Address: https://pan.baidu.com/s/1hJIbIX0r1UpI3UEtsp-6EA?pwd=jdi4 Passcode: jdi4
   
   Hifigan's Model download address:https://pan.baidu.com/s/1PGU8XEs5wy4ppJL6GjTgMQ?pwd=24g8 Passcode: 24g8
   
   More info: Trained with 1300 in game voices. About 600 Epoch.
   
   Model type: Tacotron2+hifigan

## FAQ

1. Q: Can this GUI process non-official Tacotron2 models?

   A：If the structure of the model and thinking method didn't changed, and the differences between the official and non-official is only the method when processing data, then it seems like to be mostly fine.

2. Q: Is there a command line version or HttpApi?

   A: Considering that CLI and HttpApi are prone to abuse, development has been temporarily postponed. (In version 1.0.0, **[ShiroDoMain](https://github.com/ShiroDoMain)** developed the CLI version, you can get it from the cli branch if you need it)

## Share models&Join the development!

Welcome if you want to share your models! It's not recommend to storage your models here in the Github because they may be very large. You can Pull Request with your own download address.

If you have any suggestions or discovered and bugs, please submit an issue.

## Credits

1. **[ShiroDoMain](https://github.com/ShiroDoMain)**: Developed the cli for version 1.0.0
2. **[menproject](https://github.com/menproject)**: Translation of the English README for version 1.0.0

3. **[CjangCjengh](https://github.com/CjangCjengh/)**: Provides compiled g2p tools and symbol files suitable for Japanese tonal annotation.