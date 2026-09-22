# Spectra

Drop an audio file in and it shows you the spectrum, loudness, stereo image, tempo and key. It all runs in the tab, so nothing gets uploaded.

https://bxzex.github.io/spectra/

Loudness follows BS.1770 (K-weighting, 400 ms blocks, the usual gates) and gives you integrated LUFS and loudness range. Tempo comes from autocorrelating an onset envelope between 60 and 190 BPM. Key is a chroma vector matched against the Krumhansl major and minor profiles. The FFT is hand written. Everything else is the Web Audio API.

One HTML file, no dependencies.
