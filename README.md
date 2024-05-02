# shgu0454_9103_tut5

## WEEK8 QUIZ

## Part 1: Imaging Technique Inspiration

**Imaging Technique:**

_Audio Spectrum Visualizer_

**Inspiration Source:** 

The VR video game "Beat Saber," particularly its dynamic visual effects that synchronize with the rhythm and intensity of the music. In "Beat Saber," players use virtual lightsabers to slash through blocks to the beat of a song, and the visual effects respond in real-time, creating an immersive audio-visual experience. The pulsating colors, particle effects, and reactive environment add layers of engagement and excitement to the gameplay.

**Why It's Beneficial:**

Incorporating audio-driven visual effects similar to those in "Beat Saber" can enhance the immersive qualities of the audio visualization project. By synchronizing visual elements with the rhythm and intensity of the audio, users can feel more connected to the music and experience a heightened sense of engagement. This technique not only adds entertainment value but also provides valuable feedback on audio dynamics and tempo.

![Beat Saber Sample](https://media3.giphy.com/media/JRgLEZCsivjHoRWpb2/giphy.gif?cid=6c09b952tw23igtv9hlmsa8de7phlnatvam8m1jye6mcmcsf&ep=v1_internal_gif_by_id&rid=giphy.gif&ct=g)

![Beat Saber Sample](https://img-blog.csdn.net/20170118132144415)

## Part 2: Coding Technique Exploration

**Coding Technique:**

_p5.js Audio Visualization Functions_

**How to help achieve or contribute to the desired effect**

Audio visualisation can be achieved with p5.js by using its `p5.FFT`. In p5.js, the `fft.analyze()` function does this by performing a spectral analysis of the frequencies in the audio. 

This feature provides real-time analysis of audio data, enabling dynamic visualisation of audio waveforms, spectra and amplitudes. The default microphone can also be invoked so that the image changes in response to the user's voice interaction. This allows the user to experience the synchronisation of visual and auditory elements for an interactive and interesting audio-visual experience.

```
let mic, fft;

function setup() {
  createCanvas(710, 400);
  noFill();

  mic = new p5.AudioIn();
  mic.start();
  fft = new p5.FFT();
  fft.setInput(mic);
}

function draw() {
  background(200);

  let spectrum = fft.analyze();

  beginShape();
  for (i = 0; i < spectrum.length; i++) {
    vertex(i, map(spectrum[i], 0, 255, height, 0));
  }
  endShape();
}
```

[Reference Pages and Codes](https://p5js.org/examples/sound-frequency-spectrum.html)
