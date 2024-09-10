---
layout: default
---
# Abstract
Voice Conversion (VC) technologies have advanced significantly, enabling voice cloning with just a few seconds of audio, posing serious risks to privacy, property, and reputation. In response to these threats, adversarial defense methods protect users by adding imperceptible perturbations to the audio, making it harder for VC models to clone the original voice. However, current methods are effective in white-box scenarios but struggle in black-box settings where VC models' internal parameters and structures are unknown. To address this problem, we propose a black-box adversarial defense method that effectively adapts and defends against unknown VC models relies solely on black-box feedback. We introduce a latent perturbation model that compresses speech and generates initial perturbations to reduce the search space and ensure convergence for black-box optimization. We then apply evolution-based black-box optimization to refine the perturbations, improving defense performance against unknown VC models. Extensive experiments on state-of-the-art VC models demonstrate the adaptability and superior defense performance of our method in real-world black-box scenarios compared to other defence approaches.

<center>
    <img src="./stage.png" alt="example">
</center>

## Defense against QuickVC

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

<table style="width: 100%; border-collapse: collapse;">
    <tr>
      <td></td>
      <th colspan="2" style="text-align: center;">Content utterance</th>
    </tr>
    <tr>
      <td style="text-align: center;"><i>p225_002</i></td>
      <td colspan="2" style="text-align: center;">
        <audio src="audio/chou/pair-085/content.wav" controls preload></audio>
      </td>
    </tr>
    <tr>
      <td></td>
      <th style="text-align: center;">Speaker utterance</th>
      <th style="text-align: center;">Conversion result</th>
    </tr>
    <tr>
      <td style="text-align: center;">
        <i>p333_334</i>
        <br>
        Our
      </td>
      <td style="text-align: center;">
        <audio src="audio/pertured_black_box_QuickVC/p225_002_p230_269.wav" controls preload></audio>
      </td>
      <td style="text-align: center;">
        <audio src="audio/black_box_QuickVC_test_antifakeloss/p225_002_p230_269.wav" controls preload></audio>
      </td>
    </tr>
    <tr>
      <td style="text-align: center;">
        <i>p333_334</i>
        <br>
        Antifake
      </td>
      <td style="text-align: center;">
        <audio src="audio/perture_antifake/p225_002_p230_269.wav" controls preload></audio>
      </td>
      <td style="text-align: center;">
        <audio src="audio/antifake2QuickVC/p225_002_p230_269.wav" controls preload></audio>
      </td>
    </tr>
  </table>


## Defense against TriAANVC

<table style="width: 100%; border-collapse: collapse;">
    <tr>
      <td></td>
      <th colspan="2" style="text-align: center;">Content utterance</th>
    </tr>
    <tr>
      <td style="text-align: center;"><i>p225_002</i></td>
      <td colspan="2" style="text-align: center;">
        <audio src="audio/chou/pair-085/content.wav" controls preload></audio>
      </td>
    </tr>
    <tr>
      <td></td>
      <th style="text-align: center;">Speaker utterance</th>
      <th style="text-align: center;">Conversion result</th>
    </tr>
    <tr>
      <td style="text-align: center;">
        <i>p333_334</i>
        <br>
        Our
      </td>
      <td style="text-align: center;">
        <audio src="audio/pertured_black_box_TriAANVC/p225_002_p230_216.wav" controls preload></audio>
      </td>
      <td style="text-align: center;">
        <audio src="audio/black_box_TriAANVC_test_antifakeloss/p225_002_p230_216.wav" controls preload></audio>
      </td>
    </tr>
    <tr>
      <td style="text-align: center;">
        <i>p333_334</i>
        <br>
        Antifake
      </td>
      <td style="text-align: center;">
        <audio src="audio/perture_antifake/p225_002_p230_216.wav" controls preload></audio>
      </td>
      <td style="text-align: center;">
        <audio src="audio/antifake2TriAANVC/p225_002_p230_216.wav" controls preload></audio>
      </td>
    </tr>
  </table>


## Defense against FreeVC


<table style="width: 100%; border-collapse: collapse;">
    <tr>
      <td></td>
      <th colspan="2" style="text-align: center;">Content utterance</th>
    </tr>
    <tr>
      <td style="text-align: center;"><i>p225_002</i></td>
      <td colspan="2" style="text-align: center;">
        <audio src="audio/chou/pair-085/content.wav" controls preload></audio>
      </td>
    </tr>
    <tr>
      <td></td>
      <th style="text-align: center;">Speaker utterance</th>
      <th style="text-align: center;">Conversion result</th>
    </tr>
    <tr>
      <td style="text-align: center;">
        <i>p333_334</i>
        <br>
        Our
      </td>
      <td style="text-align: center;">
        <audio src="audio/pertured_black_box-FreeVC/p225_002_p234_017.wav" controls preload></audio>
      </td>
      <td style="text-align: center;">
        <audio src="audio/black_box_FreeVC_test_antifakeloss/p225_002_p234_017.wav" controls preload></audio>
      </td>
    </tr>
    <tr>
      <td style="text-align: center;">
        <i>p333_334</i>
        <br>
        Antifake
      </td>
      <td style="text-align: center;">
        <audio src="audio/perture_antifake/p225_002_p234_017.wav" controls preload></audio>
      </td>
      <td style="text-align: center;">
        <audio src="audio/antifake2FreeVC/p225_002_p234_017.wav" controls preload></audio>
      </td>
    </tr>
  </table>

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
