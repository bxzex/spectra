# Spectra

An audio analysis suite that runs entirely in the browser tab. Drop a file in and
read its spectrum, loudness, stereo field, tempo and key. Nothing is uploaded.

Live: https://bxzex.github.io/spectra/

## What it measures

- **Integrated loudness and loudness range** — ITU-R BS.1770-4. Two stage
  K-weighting (1681 Hz high shelf, 38 Hz high pass) rendered through an
  `OfflineAudioContext`, then 400 ms mean square blocks at 75% overlap with the
  absolute (-70 LUFS) and relative (-10 LU) gates. LRA uses 3 s blocks, a -20 LU
  gate and the 10th to 95th percentile spread.
- **Sample peak** — the loudest single sample across all channels, in dBFS.
- **Tempo** — spectral flux onset envelope, mean removed, autocorrelated across
  60 to 190 BPM in quarter beat steps.
- **Key** — a chroma vector accumulated from FFT bins between 55 Hz and 2.2 kHz,
  correlated against the Krumhansl-Schmuckler major and minor profiles in all
  twelve rotations.
- **Spectrogram** — logarithmic frequency axis, 4096 point FFT, scrolling.
- **Stereo field** — a 45 degree rotated lissajous plot with the live
  correlation coefficient. Vertical is mono, horizontal is out of phase.

## Notes

No dependencies and no build step. One HTML file. The FFT is a hand written
iterative radix-2 implementation; everything else is the Web Audio API.

Built by [bxzex](https://bxzex.com).
