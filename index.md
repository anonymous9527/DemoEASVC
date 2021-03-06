---
layout: default
---

# Abstract
This paper describes an end-to-end adversarial singing voice conversion (EA-SVC) approach. It can directly generate arbitrary singing waveform by given phonetic posteriorgram (PPG) representing content, F0 representing pitch, and speaker embedding representing timbre, respectively. Proposed system is composed of three modules: generator, the audio generation discriminator, and the feature disentanglement discriminator. The generator encodes the features in parallel and inversely transforms them into the target waveform. In order to make timbre conversion more stable and controllable, speaker embedding is further decomposed to the weighted sum of a group of trainable vectors representing different timbre clusters. Further, to realize more robust and accurate singing conversion, disentanglement discriminator is proposed to remove pitch and timbre related information that remains in the encoded PPG. Finally, a two-stage training is conducted to keep a stable and effective adversarial training process. Subjective evaluation results demonstrate the effectiveness of our proposed methods. Proposed system outperforms conventional cascade approach and the WaveNet based end-to-end approach in terms of both singing quality and singer similarity. Further objective analysis reveals that the model trained with the proposed two-stage training strategy can produce a smoother and sharper formant which leads to higher audio quality. 

# Audio Samples

These models are presented:
- WaveNet: The WaveNet based end-to-end SVC approach.
- C-SVC: conventional cascade SVC approach
- EA-SVC: the proposed end-to-end adversarial SVC approach.
    - EA-SVC-1: EA-SVC without decomposition & feature disentanglement
    - EA-SVC-2: EA-SVC without feature disentanglement

## Singing Voice Conversion for Unseen Singers

### Male to male

<table align="center">
    <tr><th>Source</th><th>Target</th></tr>
    <tr>
        <td><audio controls style="width: 150px;"><source src="sample/source/jmlongspk001312-jmlongsong001312-0.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/target/125835260_120691_3.wav"></audio></td>
    </tr>
</table>

#### Use original pitch

<table align="center">
    <tr><th>WaveNet</th><th>C-SVC</th><th>EA-SVC</th></tr>
    <tr>
        <td><audio controls style="width: 150px;"><source src="sample/wavenet/jmlongspk001312-jmlongsong001312-0_0_125835260_120691_3.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/c-svc/jmlongspk001312-jmlongsong001312-0_0_125835260_120691_3.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/ea-svc/jmlongspk001312-jmlongsong001312-0_0_125835260_120691_3.wav"></audio></td>
    </tr>
</table>

#### Use shifted pitch

<table align="center">
    <tr><th>WaveNet</th><th>C-SVC</th><th>EA-SVC</th></tr>
    <tr>
        <td><audio controls style="width: 150px;"><source src="sample/wavenet/jmlongspk001312-jmlongsong001312-0_1_125835260_120691_3.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/c-svc/jmlongspk001312-jmlongsong001312-0_1_125835260_120691_3.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/ea-svc/jmlongspk001312-jmlongsong001312-0_1_125835260_120691_3.wav"></audio></td>
    </tr>
</table>

### Male to female

<table align="center">
    <tr><th>Source</th><th>Target</th></tr>
    <tr>
        <td><audio controls style="width: 150px;"><source src="sample/source/jmlongspk000501-jmlongsong000501-0.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/target/220313220_2457204_3.wav"></audio></td>
    </tr>
</table>

#### Use original pitch

<table align="center">
    <tr><th>WaveNet</th><th>C-SVC</th><th>EA-SVC</th></tr>
    <tr>
        <td><audio controls style="width: 150px;"><source src="sample/wavenet/jmlongspk000501-jmlongsong000501-0_0_220313220_2457204_3.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/c-svc/jmlongspk000501-jmlongsong000501-0_0_220313220_2457204_3.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/ea-svc/jmlongspk000501-jmlongsong000501-0_0_220313220_2457204_3.wav"></audio></td>
    </tr>
</table>

#### Use shifted pitch

<table align="center">
    <tr><th>WaveNet</th><th>C-SVC</th><th>EA-SVC</th></tr>
    <tr>
        <td><audio controls style="width: 150px;"><source src="sample/wavenet/jmlongspk000501-jmlongsong000501-0_1_220313220_2457204_3.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/c-svc/jmlongspk000501-jmlongsong000501-0_1_220313220_2457204_3.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/ea-svc/jmlongspk000501-jmlongsong000501-0_1_220313220_2457204_3.wav"></audio></td>
    </tr>
</table>

### Female to female

<table align="center">
    <tr><th>Source</th><th>Target</th></tr>
    <tr>
        <td><audio controls style="width: 150px;"><source src="sample/source/jmlongspk000002-jmlongsong000002-0.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/target/107780550_4460473_3.wav"></audio></td>
    </tr>
</table>

#### Use original pitch

<table align="center">
    <tr><th>WaveNet</th><th>C-SVC</th><th>EA-SVC</th></tr>
    <tr>
        <td><audio controls style="width: 150px;"><source src="sample/wavenet/jmlongspk000002-jmlongsong000002-0_0_107780550_4460473_3.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/c-svc/jmlongspk000002-jmlongsong000002-0_0_107780550_4460473_3.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/ea-svc/jmlongspk000002-jmlongsong000002-0_0_107780550_4460473_3.wav"></audio></td>
    </tr>
</table>

#### Use shifted pitch

<table align="center">
    <tr><th>WaveNet</th><th>C-SVC</th><th>EA-SVC</th></tr>
    <tr>
        <td><audio controls style="width: 150px;"><source src="sample/wavenet/jmlongspk000002-jmlongsong000002-0_1_107780550_4460473_3.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/c-svc/jmlongspk000002-jmlongsong000002-0_1_107780550_4460473_3.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/ea-svc/jmlongspk000002-jmlongsong000002-0_1_107780550_4460473_3.wav"></audio></td>
    </tr>
</table>

### Female to male

<table align="center">
    <tr><th>Source</th><th>Target</th></tr>
    <tr>
        <td><audio controls style="width: 150px;"><source src="sample/source/jmlongspk001419-jmlongsong001419-0.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/target/177857410_316_0.wav"></audio></td>
    </tr>
</table>

#### Use original pitch

<table align="center">
    <tr><th>WaveNet</th><th>C-SVC</th><th>EA-SVC</th></tr>
    <tr>
        <td><audio controls style="width: 150px;"><source src="sample/wavenet/jmlongspk001419-jmlongsong001419-0_0_177857410_316_0.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/c-svc/jmlongspk001419-jmlongsong001419-0_0_177857410_316_0.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/ea-svc/jmlongspk001419-jmlongsong001419-0_0_177857410_316_0.wav"></audio></td>
    </tr>
</table>

#### Use shifted pitch

<table align="center">
    <tr><th>WaveNet</th><th>C-SVC</th><th>EA-SVC</th></tr>
    <tr>
        <td><audio controls style="width: 150px;"><source src="sample/wavenet/jmlongspk001419-jmlongsong001419-0_1_177857410_316_0.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/c-svc/jmlongspk001419-jmlongsong001419-0_1_177857410_316_0.wav"></audio></td>
        <td><audio controls style="width: 150px;"><source src="sample/ea-svc/jmlongspk001419-jmlongsong001419-0_1_177857410_316_0.wav"></audio></td>
    </tr>
</table>

## Timbre Transfer

<table align="center">
    <tr><th>alpha = 0</th><th>alpha = 0.25</th><th>alpha = 0.5</th><th>alpha = 0.75</th><th>alpha = 1.0</th></tr>
    <tr>
        <td><audio controls style="width: 100px;"><source src="sample/timbre/000.wav"></audio></td>
        <td><audio controls style="width: 100px;"><source src="sample/timbre/025.wav"></audio></td>
        <td><audio controls style="width: 100px;"><source src="sample/timbre/050.wav"></audio></td>
        <td><audio controls style="width: 100px;"><source src="sample/timbre/075.wav"></audio></td>
        <td><audio controls style="width: 100px;"><source src="sample/timbre/100.wav"></audio></td>
    </tr>
</table>

## Pitch Control

<table align="center">
    <tr><th>alpha = 0.5</th><th>alpha = 0.8</th><th>alpha = 1.0</th><th>alpha = 1.2</th><th>alpha = 1.5</th></tr>
    <tr>
        <td><audio controls style="width: 100px;"><source src="sample/pitch/05.wav"></audio></td>
        <td><audio controls style="width: 100px;"><source src="sample/pitch/08.wav"></audio></td>
        <td><audio controls style="width: 100px;"><source src="sample/pitch/10.wav"></audio></td>
        <td><audio controls style="width: 100px;"><source src="sample/pitch/12.wav"></audio></td>
        <td><audio controls style="width: 100px;"><source src="sample/pitch/15.wav"></audio></td>
    </tr>
</table>
