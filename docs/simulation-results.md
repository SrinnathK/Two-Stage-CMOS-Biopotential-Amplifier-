# Simulation Results and Calculations

**Author: Srinnath Krishnan**

This document summarizes the design metrics and the equations used to calculate gain, transconductance efficiency, common-mode rejection, bandwidth, transient gain, and noise.

## 1. Design values

| Quantity | Value |
|---|---:|
| Midband voltage gain | 39.6 dB |
| Linear voltage gain | Approximately 95.5 V/V |
| Bandwidth | 45 MHz |
| Current | 398 nA |
| Power consumption | 5 nW |
| $g_m/I_D$ | 35.9 V$^{-1}$ |
| CMRR | 51.38 dB |
| First-stage tail current | Approximately 6 µA |
| First-stage input-pair $g_m$ | Approximately 82 µS |
| First-stage $g_m/I_D$ | Approximately 27 V$^{-1}$ |
| First-stage open-loop gain | Approximately 31.8 dB |
| First-stage unity-gain frequency | Approximately 7 GHz |

## 2. Voltage gain: decibels to linear scale

Voltage gain is

$$
A_v = \frac{V_{out}}{V_{in}}
$$

Voltage gain in decibels is

$$
A_{v,\mathrm{dB}} = 20\log_{10}|A_v|
$$

Rearranging gives

$$
|A_v| = 10^{A_{v,\mathrm{dB}}/20}
$$

For a midband gain of 39.6 dB,

$$
|A_v| = 10^{39.6/20} = 10^{1.98} \approx 95.5
$$

The corresponding linear voltage gain is approximately **95.5 V/V**.

## 3. Cascaded two-stage gain

For two cascaded stages,

$$
A_{v,\mathrm{total}} = A_{v1}A_{v2}
$$

When stage gains are expressed in decibels, the total gain is

$$
A_{v,\mathrm{total,dB}} = A_{v1,\mathrm{dB}} + A_{v2,\mathrm{dB}}
$$

## 4. Power consumption

The DC power consumption relationship is

$$
P = V_{DD} I_{DD}
$$

The design metrics list power consumption as **5 nW** and current as **398 nA**.

## 5. Transconductance efficiency

Transconductance efficiency is defined as

$$
\frac{g_m}{I_D}
$$

where $g_m$ is small-signal transconductance and $I_D$ is drain current. The unit is V$^{-1}$.

Using the first-stage values $g_m \approx 82\,\mu\mathrm{S}$ and $g_m/I_D \approx 27\,\mathrm{V}^{-1}$,

$$
I_D = \frac{g_m}{g_m/I_D}
= \frac{82\,\mu\mathrm{S}}{27\,\mathrm{V}^{-1}}
\approx 3.04\,\mu\mathrm{A}
$$

This corresponds to approximately 3 µA per branch.

## 6. Common-mode rejection ratio (CMRR)

CMRR is the ratio of differential-mode gain magnitude to common-mode gain magnitude:

$$
\mathrm{CMRR} = \left|\frac{A_d}{A_{cm}}\right|
$$

In decibels,

$$
\mathrm{CMRR}_{\mathrm{dB}} = 20\log_{10}\left|\frac{A_d}{A_{cm}}\right|
$$

When both gains are expressed in dB,

$$
\mathrm{CMRR}_{\mathrm{dB}} = A_{d,\mathrm{dB}} - A_{cm,\mathrm{dB}}
$$

Using the design gain values,

$$
39.8 - (-11.58) = 51.38\,\mathrm{dB}
$$

The resulting CMRR is **51.38 dB**.

## 7. Bandwidth and cutoff frequency

For a low-pass response, the conventional -3 dB cutoff frequency satisfies

$$
|A_v(f_c)| = \frac{|A_{v,\mathrm{mid}}|}{\sqrt{2}}
\approx 0.707|A_{v,\mathrm{mid}}|
$$

For a band-pass response, bandwidth is

$$
BW = f_H - f_L
$$

where $f_L$ and $f_H$ are the lower and upper cutoff frequencies. The design bandwidth is **45 MHz**.

## 8. Transient voltage gain

Using steady-state peak-to-peak input and output amplitudes,

$$
|A_v| = \frac{V_{out,pp}}{V_{in,pp}}
$$

The corresponding gain in decibels is

$$
A_{v,\mathrm{dB}} = 20\log_{10}\left(\frac{V_{out,pp}}{V_{in,pp}}\right)
$$

## 9. Noise and input-referred noise

Input-referred voltage-noise spectral density is obtained from output noise using

$$
v_{n,\mathrm{in}}(f) = \frac{v_{n,\mathrm{out}}(f)}{|A_v(f)|}
$$

Integrated RMS noise over a frequency range is

$$
v_{n,\mathrm{rms}} = \sqrt{\int_{f_L}^{f_H} S_v(f)\,df}
$$

where $S_v(f)$ is the input-referred voltage-noise power spectral density in V$^2$/Hz.
