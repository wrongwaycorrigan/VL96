<div align="center">

# VL96

**A breath-controlled physical-modeling wind instrument for REAPER**

<p>
  <img src="https://img.shields.io/badge/status-experimental-orange?style=for-the-badge" alt="Status: experimental">
  <img src="https://img.shields.io/badge/version-1.42-blue?style=for-the-badge" alt="Version 1.42">
  <img src="https://img.shields.io/badge/REAPER-JSFX-4a90d9?style=for-the-badge" alt="REAPER JSFX">
</p>
<p>
  <img src="https://img.shields.io/badge/synthesis-digital%20waveguide-6c5ce7?style=flat-square" alt="Synthesis: digital waveguide">
  <img src="https://img.shields.io/badge/input-breath%20controller-2ecc71?style=flat-square" alt="Input: breath controller">
  <img src="https://img.shields.io/badge/samples-none-lightgrey?style=flat-square" alt="Samples: none">
</p>

<i>No oscillators, no samples — just air, a reed and a tube, simulated in real time.</i>

</div>

---

> [!WARNING]
> **Experimental.** VL96 is a research project in active development. Sounds, controls and presets change between versions, and some notes or settings may still squeak, flutter or behave unexpectedly. Save your projects with the version you used.

## What it is

VL96 is a monophonic wind synthesizer for wind controllers such as the Roland Aerophone AE-20. Instead of playing back recordings, it models how an instrument actually makes sound: breath pressure drives a reed or air jet, which excites a resonating tube, and the tube's reflections feed back to sustain the note. The aim is the expressive, slightly characterful sound of the early-'90s physical-modeling synths rather than a clinical simulation.

**Voices:** Clarinet · Sax · Flute · Oboe · Shakuhachi · Sax II (two-tube cone, experimental)

## The research behind it

<table>
  <tr>
    <td width="34%"><b>Digital waveguides</b></td>
    <td>Julius O. Smith III's waveguide synthesis at Stanford's CCRMA: a tube modeled as delay lines carrying sound waves in both directions, with filters for losses at the ends. See <a href="https://ccrma.stanford.edu/~jos/pasp/"><i>Physical Audio Signal Processing</i></a>.</td>
  </tr>
  <tr>
    <td><b>Reed and jet models</b></td>
    <td>The reed "reflection table" and air-jet nonlinearity in the tradition of the <a href="https://ccrma.stanford.edu/software/stk/">Synthesis ToolKit (STK)</a> by Perry Cook and Gary Scavone, building on McIntyre, Schumacher and Woodhouse's classic work on self-sustained oscillation in musical instruments.</td>
  </tr>
  <tr>
    <td><b>The two-tube cone</b></td>
    <td>The insight that a truncated cone (a saxophone body) behaves like two cylinders joined in parallel at the reed, which made conical-bore instruments practical in real time. VL96's Sax II is an original implementation of this idea, inspired by the published patent <a href="https://patents.google.com/patent/US5438156A">US 5,438,156</a>.</td>
  </tr>
  <tr>
    <td><b>Fractional delays</b></td>
    <td>Thiran allpass interpolation for smooth, in-tune pitch without dulling the tone.</td>
  </tr>
  <tr>
    <td><b>Listening analysis</b></td>
    <td>Presets were tuned by measuring publicly available demo recordings of 1990s modeling synths: harmonic balance, vibrato, breath noise and the cycle-to-cycle "turbulence" that makes a tone feel alive. No manufacturer voice data or firmware was used.</td>
  </tr>
</table>

## Playing it

| Feature | What breath and velocity do |
|---|---|
| **Breath air** | Audible air in the softest dynamics, fading as you play into the tone |
| **Bloom & Sens** | Push past the Sens point and the tone opens up |
| **Reso** | A resonant peak that climbs and sharpens with breath |
| **Pitch** | Slightly flat when soft, slightly sharp when pushed, as on a real instrument |
| **Attack** | Velocity sets how crisp each tongued note starts |

## Install

1. Copy `VL96.jsfx` into your REAPER `Effects` folder (*Options → Show REAPER resource path*).
2. Add **VL96** to a track as an instrument and arm it for MIDI input.
3. Send breath as **CC2** (or CC11 / velocity, chosen under *Breath Source*).

## Disclaimer

VL96 is an independent project and is not affiliated with, endorsed by or derived from Yamaha Corporation or Roland Corporation. Product names mentioned are trademarks of their respective owners and are used only to describe the research context.
