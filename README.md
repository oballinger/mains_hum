# Mains Hum Scope

A browser page that listens for mains hum through your phone or laptop microphone, measures the mains frequency from it, and compares it live with the official GB grid frequency (Elexon BMRS `FREQ`, 15 s readings, about 1 minute delay).

**Live:** https://oballinger.github.io/mains_hum/

- **Microphone:** mixes each harmonic of 50 Hz (50 to 300 Hz) down to 0 Hz in an AudioWorklet, finds the peak with a sliding DFT, and weights the harmonics by strength.
- **Camera (experimental):** reads rolling-shutter flicker bands. Most phone and laptop cameras lock exposure to multiples of 10 ms in 50 Hz countries, which cancels the flicker, so this rarely locks.
- **Photodiode:** only when served locally by `server.py` with an ESP32 attached.

Tips: allow the microphone, keep the room quiet, and hold the device near something that hums (a charger, a fridge, a lamp driver). Only meaningful in Great Britain, since it compares against the GB grid.
