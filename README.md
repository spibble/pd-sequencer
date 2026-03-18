# Pd Sequencer

<p align="center">
  <img src="/public/sequencer.png" width="80%"></img>
</p>

This is my final project for UCSD's MUS 171. It is an implementation of a multi-channel sequencer using Puredata. Everything related to the implementation is in `sequencer/` and the "main patch" which runs everything is `drum_sqncr.pd`.

By default, there are 4 channels of sequencers, each connected to a sampler which loads in a `.wav` file and can apply effects such as bitcrushing and frequency filtering. The sequencer itself provides some additional signal parameters such as volume and panning for left and right stereo channels. There are some example samples which I have included, but new samples can be added to the `samples/` directory and then loaded in to the samplers. Helper abstractions within the main objects can be found in `util/` and the main objects themselves are in `modules/`.

However, part of the design of the sequencer was to make things modular and self-contained. So, it is very easy to intialize another sequencer, hook it up to another sampler, and now you have added an extra channel! Theoretically, this means one can sequence an unlimited number of channels, though at some point Pd may struggle to keep up.

You can play each sample/sequencer manually using the orange bangs or keyboard controls (make sure to toggle **keyboard playback** on in the main patch), or you can use the control panel at the top to automatically start/toggle looping for all connected channels. As such, if you wish to add more channels don't forget to hook them up to the conrrol panel for easy handling of all the channels.

## Things I learned
- Basic Pd UI design, including some graph-on-parent and canvas object tricks
- Smooth panning using a linear function and later using sine and cosine functions
- How to implement a bitcrush effect via quantization and renormalization of audio signals
- Managing multiple instances of the same abstraction via instance ID variable naming (i.e. `$0` spam)
- Using `keyup` for reading in keyboard input
