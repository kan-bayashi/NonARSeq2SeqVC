---
date: 2020-10-25T00:00:00+09:00
type: "index"
---

# Non-autoregressive sequence-to-sequence voice conversion

- Tomoki Hayashi (TARVO Inc. / Nagoya University)
- Wen-Chin Huang (Nagoya University)
- Kazuhiro Kobayashi (TARVO Inc. / Nagoya University)
- Tomoki Toda (Nagoya University)

## Abstract

![](figs/overview.png)

This paper proposes a novel voice conversion (VC) method based on non-autoregressive sequence-to-sequence (NAR-S2S) models. Inspired by the great success of NAR-S2S models such as FastSpeech in text-to-speech (TTS), we extend the FastSpeech2 model for the VC problem. We introduce the convolution-augmented Transformer (Conformer) instead of the Transformer, making it possible to capture both local and global context information from the input sequence. Furthermore, we extend variance predictors to variance converters to explicitly convert the source speaker's prosody components such as pitch and energy into the target speaker. The experimental evaluation with the Japanese speaker dataset, which consists of male and female speakers of 1,000 utterances, demonstrates that the proposed model enables us to perform more stable, faster, and better conversion than autoregressive S2S (AR-S2S) models such as Tacotron2 and Transformer.

## Audio samples (Japanese)

- **Target**: Target speech (24,000 Hz).
- **Tacotron2**: Converted speech by Tacotron2-based AR-S2S model.
- **Transformer**: Converted speech by Transformer-based AR-S2S model.
- **Proposed**: Converted speech by the proposed NAR-S2S model.

The neural vocoder is the same among the models.  
We use [ParallelWaveGAN](https://github.com/kan-bayashi/ParallelWaveGAN) as the neural vocoder.

#### たとえば、プログラムを書く仕事は、機械なしでも、やろうと思えばできる。

| Male->Female | Female->Male |
| --- | --- |
| **Target** | **Target** |
|<audio controls="" ><source src="audio/female_gt/ETRAB00976.wav"/></audio>|<audio controls="" ><source src="audio/male_gt/ETRAB00976.wav"/></audio>| |
| **Tacotron2** | **Tacotron2** |
|<audio controls="" ><source src="audio/tacotron2_m2f/ETRAB00976_gen.wav"/></audio>|<audio controls="" ><source src="audio/tacotron2_f2m/ETRAB00976_gen.wav"/></audio>| |
| **Transformer** | **Transformer** |
|<audio controls="" ><source src="audio/transformer_m2f/ETRAB00976_gen.wav"/></audio>|<audio controls="" ><source src="audio/transformer_f2m/ETRAB00976_gen.wav"/></audio>| |
| **Propoed** | **Proposed** |
|<audio controls="" ><source src="audio/conformer_fastspeech2_m2f/ETRAB00976_gen.wav"/></audio>|<audio controls="" ><source src="audio/conformer_fastspeech2_f2m/ETRAB00976_gen.wav"/></audio>| |

#### そのうちに、日が暮れて、寒い風が、ヒューヒュー、吹きはじめました。

| Male->Female | Female->Male |
| --- | --- |
| **Target** | **Target** |
|<audio controls="" ><source src="audio/female_gt/ETRAB00982.wav"/></audio>|<audio controls="" ><source src="audio/male_gt/ETRAB00982.wav"/></audio>| |
| **Tacotron2** | **Tacotron2** |
|<audio controls="" ><source src="audio/tacotron2_m2f/ETRAB00982_gen.wav"/></audio>|<audio controls="" ><source src="audio/tacotron2_f2m/ETRAB00982_gen.wav"/></audio>| |
| **Transformer** | **Transformer** |
|<audio controls="" ><source src="audio/transformer_m2f/ETRAB00982_gen.wav"/></audio>|<audio controls="" ><source src="audio/transformer_f2m/ETRAB00982_gen.wav"/></audio>| |
| **Propoed** | **Proposed** |
|<audio controls="" ><source src="audio/conformer_fastspeech2_m2f/ETRAB00982_gen.wav"/></audio>|<audio controls="" ><source src="audio/conformer_fastspeech2_f2m/ETRAB00982_gen.wav"/></audio>| |

#### 小柄な男は、部屋の中を、しげしげと、覗き込みながら言った。

| Male->Female | Female->Male |
| --- | --- |
| **Target** | **Target** |
|<audio controls="" ><source src="audio/female_gt/ETRAB00990.wav"/></audio>|<audio controls="" ><source src="audio/male_gt/ETRAB00990.wav"/></audio>| |
| **Tacotron2** | **Tacotron2** |
|<audio controls="" ><source src="audio/tacotron2_m2f/ETRAB00990_gen.wav"/></audio>|<audio controls="" ><source src="audio/tacotron2_f2m/ETRAB00990_gen.wav"/></audio>| |
| **Transformer** | **Transformer** |
|<audio controls="" ><source src="audio/transformer_m2f/ETRAB00990_gen.wav"/></audio>|<audio controls="" ><source src="audio/transformer_f2m/ETRAB00990_gen.wav"/></audio>| |
| **Propoed** | **Proposed** |
|<audio controls="" ><source src="audio/conformer_fastspeech2_m2f/ETRAB00990_gen.wav"/></audio>|<audio controls="" ><source src="audio/conformer_fastspeech2_f2m/ETRAB00990_gen.wav"/></audio>| |

## Author

Tomoki Hayashi ([@kan-bayashi](https://github.com/kan-bayashi))  
e-mail: hayashi.tomoki@g.sp.m.is.nagoya-u.ac.jp
