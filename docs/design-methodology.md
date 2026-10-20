# Design Methodology

**Author: Srinnath Krishnan**

## 1. Objective

Design and simulate a two-stage CMOS amplifier for low-amplitude biopotential signals, focusing on voltage gain, frequency response, transconductance efficiency, common-mode rejection, noise, and power consumption.

## 2. Architecture

### First stage: operational transconductance amplifier

The first stage uses an OTA architecture with a differential input pair, current-mirror load, and bias network. Weak-inversion operation supports high transconductance efficiency at low current. Capacitive feedback provides gain control, while MOS pseudo-resistors provide very high resistance for low-frequency behavior and DC-offset rejection.

First-stage design values:

- Tail current: approximately 6 µA, or approximately 3 µA per branch.
- Input-pair transconductance: approximately 82 µS.
- Transconductance efficiency: approximately 27 V$^{-1}$.
- Open-loop gain: approximately 31.8 dB.
- Unity-gain frequency: approximately 7 GHz.

### Second stage: cascode amplifier

The second stage uses a common-source device followed by a common-gate device. The cascode arrangement increases output resistance and voltage gain. Biasing maintains the intended transistor operating regions, and the complete circuit is evaluated for frequency response and loading.

## 3. Simulation workflow

1. Run DC operating-point analysis to inspect transistor terminal voltages and operating regions.
2. Run AC analysis to evaluate gain and frequency response.
3. Run transient analysis to examine time-domain behavior.
4. Run differential-mode and common-mode analyses to evaluate CMRR.
5. Run noise analysis to examine the noise spectrum.
6. Evaluate supply current and power consumption.
7. Save the schematic and simulation plots alongside the design documentation.

## 4. Project scope

The repository organizes the circuit schematic, simulation screenshots, design methodology, and calculated results for convenient review.
