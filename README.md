# Pd Sequencer

<p align="center">
  <img src="/public/sequencer.png" width="80%"></img>
</p>

This is my final project for UCSD's MUS 171. It is an implementation of a multi-channel sequencer using Puredata. The "main" patch that runs everything is `drum_sqqncr/drum_sqncr.pd`.

By default, there are 4 channels of sequencers, each connected to a sampler which loads in a `.wav` file and can apply effects such as bitcrushing and frequency filtering. There are some example samples which I have included, but new samples can be added to the `samples/` directory and then loaded in to the samplers. Helper abstractions within the main objects can be found in `util/` and the main objects themselves are in `modules/`.

## Things I learned
- Basic Pd UI design, including some graph-on-parent and canvas object tricks
- Smooth panning using a linear function and later using sine and cosine functions
- How to implement a bitcrush effect via quantization and renormalization of audio signals
- Managing multiple instances of the same abstraction via instance ID variable naming (i.e. `$0` spam)
- Using `keyup` for reading in keyboard input
