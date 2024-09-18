---
layout: default
---
# Abstract
Voice Conversion (VC) technologies have advanced significantly, enabling voice cloning with just a few seconds of audio, posing serious risks to privacy, property, and reputation. In response to these threats, adversarial defense methods protect users by adding imperceptible perturbations to the audio, making it harder for VC models to clone the original voice. However, current methods are effective in white-box scenarios but struggle in black-box settings where VC models' internal parameters and structures are unknown. To address this problem, we propose a black-box adversarial defense method that effectively adapts and defends against unknown VC models relies solely on black-box feedback. We introduce a latent perturbation model that compresses speech and generates initial perturbations to reduce the search space and ensure convergence for black-box optimization. We then apply evolution-based black-box optimization to refine the perturbations, improving defense performance against unknown VC models. Extensive experiments on state-of-the-art VC models demonstrate the adaptability and superior defense performance of our method in real-world black-box scenarios compared to other defense approaches.

<center>
    <img src="./stage.png" alt="example">
</center>

# Evaluation
This demo showcases the defense effects of different defense methods against three different voice conversion models in a black-box scenario. Here, "attack-vc" and "antifake" refer to the official implementations of Attack-VC and Antifake, respectively, while "voiceguard" was implemented by ourselves based on the original paper, as the authors did not provide complete code. "Ours" refers to the method we proposed, and "ours (stage-1)" indicates that the protected samples are generated solely through stage-1. For comparison, we set the content of all voice conversions to be the same: "Ask her to bring these things with her from the store."

## Defense against QuickVC


<table style="width: 100%; border-collapse: collapse;">
    <tr>
        <td></td>
        <th colspan="2" style="text-align: center; vertical-align: middle">Origin Speaker utterance</th>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle"><i>p230_269</i></td>
        <td colspan="2" style="text-align: center; vertical-align: middle">
            <audio src="audio/origin/p230_269.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td></td>
        <th style="text-align: center; vertical-align: middle">Protected Speaker utterance</th>
        <th style="text-align: center; vertical-align: middle">Conversion result</th>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p230_269</i><br><b>Attack-VC</b>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/pertured_attackvc/p225_002_p230_269.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/attackvc2QuickVC/p225_002_p230_269.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p230_269</i><br><b>VoiceGuard</b>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/pertured_voiceguard/p225_002_p230_269.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/voiceguard2QuickVC/p225_002_p230_269.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p230_269</i><br><b>Antifake</b>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/perture_antifake/p225_002_p230_269.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/antifake2QuickVC/p225_002_p230_269.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p230_269</i><br><b>Our(stage-1)</b>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/pertured_gen_once/p225_002_p230_269.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/gen_once2QuickVC/p225_002_p230_269.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p230_269</i><br>Our
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/pertured_black_box_QuickVC/p225_002_p230_269.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/black_box_QuickVC_test_antifakeloss/p225_002_p230_269.wav" controls preload></audio>
        </td>
    </tr>
</table>

## Defense against TriAANVC

<table style="width: 100%; border-collapse: collapse;">
    <tr>
        <td></td>
        <th colspan="2" style="text-align: center; vertical-align: middle">Origin Speaker utterance</th>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle"><i>p330_213</i></td>
        <td colspan="2" style="text-align: center; vertical-align: middle">
            <audio src="audio/origin/p330_213.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td></td>
        <th style="text-align: center; vertical-align: middle">Protected Speaker utterance</th>
        <th style="text-align: center; vertical-align: middle">Conversion result</th>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p330_213</i><br><b>Attack-VC</b>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/pertured_attackvc/p225_002_p330_213.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/attackvc2TriAANVC/p225_002_p330_213.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p330_213</i><br><b>VoiceGuard</b>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/pertured_voiceguard/p225_002_p330_213.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/voiceguard2TriAANVC/p225_002_p330_213.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p330_213</i><br><b>Antifake</b>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/perture_antifake/p225_002_p330_213.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/antifake2TriAANVC/p225_002_p330_213.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p330_213</i><br><b>Our(stage-1)</b>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/pertured_gen_once/p225_002_p330_213.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/gen_once2TriAANVC/p225_002_p330_213.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p330_213</i><br>Our
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/pertured_black_box_TriAANVC/p225_002_p330_213.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/black_box_TriAANVC_test_antifakeloss/p225_002_p330_213.wav" controls preload></audio>
        </td>
    </tr>
</table>

## Defense against FreeVC

<table style="width: 100%; border-collapse: collapse;">
    <tr>
        <td></td>
        <th colspan="2" style="text-align: center; vertical-align: middle">Origin Speaker utterance</th>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle"><i>p279_130</i></td>
        <td colspan="2" style="text-align: center; vertical-align: middle">
            <audio src="audio/origin/p279_130.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td></td>
        <th style="text-align: center; vertical-align: middle">Protected Speaker utterance</th>
        <th style="text-align: center; vertical-align: middle">Conversion result</th>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p279_130</i><br><b>Attack-VC</b>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/pertured_attackvc/p225_002_p279_130.wav.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/attackvc2FreeVC/p225_002_p279_130.wav.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p279_130</i><br><b>VoiceGuard</b>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/pertured_voiceguard/p225_002_p279_130.wav.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/voiceguard2FreeVC/p225_002_p279_130.wav.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p279_130</i><br><b>Antifake</b>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/perture_antifake/p225_002_p279_130.wav.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/antifake2FreeVC/p225_002_p279_130.wav.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p279_130</i><br><b>Our(stage-1)</b>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/pertured_gen_once/p225_002_p279_130.wav.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/gen_once2FreeVC/p225_002_p279_130.wav.wav" controls preload></audio>
        </td>
    </tr>
    <tr>
        <td style="text-align: center; vertical-align: middle">
            <i>p279_130</i><br>Our
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/pertured_black_box-FreeVC/p225_002_p279_130.wav.wav" controls preload></audio>
        </td>
        <td style="text-align: center; vertical-align: middle">
            <audio src="audio/black_box_FreeVC_test_antifakeloss/p225_002_p279_130.wav.wav" controls preload></audio>
        </td>
    </tr>
</table>