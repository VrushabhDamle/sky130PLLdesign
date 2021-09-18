# Phase-Locked Loop(PLL) IC design on Open-Source Google-Skywater 130nm Workshop

[![PLL-Workshop-Banner_efabless](https://user-images.githubusercontent.com/89193562/133880800-c6d948ca-9918-4637-bc68-8d563b887694.png)](https://www.vlsisystemdesign.com/pll-design-using-sky130/)

## Brief Description of the Workshop

# Day 1: PLL Theory and Lab setup

## Part 1: Introduction to PLL

- To get a precise clock signal without frequency or phase noise and at the same time it has the flexibility of running at a frequency of our choice.
- Two ways in which clock signal can be generated for our application:
    - Quartz crystals
    - Voltage Controlled Oscillators
- Quartz Crysatals have a pure spectrum (there aren't any unwanted frequencies). However, it is designed to give only a certain frequency output and they aren't flexible like the Voltage Controlled Oscillators.
- Voltage Controlled Oscillator can be implemented on chip easily with inverters and the frequency can be controlled with an input voltage. However, they tend to have noise or fluctuations in their phase.
- The purpose of PLL is to make the spectrum of a Voltage Controlled Oscillator pure while still maintaining the flexibility.


- Phase-Locked Loop Intuition:
    - To mimic the reference means to have the same/a multiple of the reference frequency and a constant phase difference with it.


- Components of a basic PLL are:
    - **VCO (Voltage Controlled Oscillator)**: It is the on-chip oscillator.
    - **PFD (Phase Frequency Detector)**: It takes care of the comparison of the output signal and the reference signal.
    - **CP (Charge Pump)**: It converts the digital comparison output of the PFD into an analog signal that converts the frequency of the VCO
    - **LPF (Low Pass Filter)**: It serves to smoothen the CP output signal. It also has a much bigger role in sustainability of the feedback load.
    - **FD (Frequency Divider)**: It converts the whole system into a frequency multiplier.
    - Such a PLL is called as a **Clock Multiplier PLL**.

## Part 2: Introduction to Phase Frequency Detector

- When we use the XOR function on the reference signal and the output signal, if the phase increases then the width of the pulse of the XOR signal also increases.
- So the width of the XOR pulse can be used as a measure of the phase difference.
- XOR operation doesn't distinguish between which signal is leading and lagging.
- The ability to distinguish between lagging and leading signal is essential for designing a PLL.
- This can be achieved by using two signals \- Up and Down signals
