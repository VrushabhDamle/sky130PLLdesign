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
- Down signal is activated if the falling edge of the output signal is obtained before the falling edge of the reference signal and it stays active until the falling edge of the reference signal is received.
- UP signal is activated if the falling edge of the reference signal is obtained before the falling edge of the output signal and it stays active until the falling edge of the output signal is received.
- This can be depicted in the state machine format as follows:


- A good way to detect falling or rising edge is by usng a flip flop
- Implementing the circuit with flip flops:
    - The negative edge flip flops are used here. In this case, it is known that if the clock input falls, the flip flop output will go high. This indicates the falling edge.
    - Two flip flops are required because of the need to detect the falling edge of two different signals in different scenarios.
    - Now, from the state diagram, the falling edge of the reference signal arrives and then the falling edge of the output signal arrives. Both up and down signals should now become low. To get this, an additional AND gate is required.




- This is one of the boost phase detector circuits.
- There is and issue with the circuit \- **Dead Zone**:
    - Dead Zone prevents us from improving the smallest difference in phase or frequency that the PFD is able to measure.
    - If the signals are very close, then we get an output which is clipped as there isn't enough time for it to rise.
    - A more precise PFD enables better stability for the PLL because it enables minute adjustments of the phase and frequency.

## Introduction to Charge Pump

- The role of a CP in PLL is to convert the difference in phase or frequency which is measured digitally into an analog signal that can be used to control the VCO.
- It can be done by using current steering circuits. A current steering circuit steers the current or it directs the current flow from the Vdd to the output or from the output to the ground based on the up or down signal that is provided.
- If up signal is active, the current flows from the Vdd to the output capacitor and charges the output. This increases the voltage at the CP output.
- If down signal is active, the current flows from the output capacitor to the ground and discharges the output. This decreases the voltage at the CP output.
- The reluctance of the capacitor to change voltage quickly, smoothens or averages the voltage change at the output so when the average active time of the up signal is higher than the down signal, the output voltage rises.
- Similarly, when average active time of down signal is higher than the up signal, the output voltage falls.
- Increasing the voltage speeds up the VCO while reduction involtage slows it down.
- When the up and down transistors are off, there is still a small current flowing through them in the form of leakage current. This leakage current has a bad impact on output control voltage because it keeps charging the output capacitor even when there is no up or down signal.
- The averaging is still not as smooth as required. There are still fluctuations caused according to the rise and fall of the up and down signals. We can tackle this by replacing the output capacitor with a low pass filter.
- This smoothens out any high frequency fluctuations in the output. LPF has a very significant role in stabilizing the PLL. Without the load filter, the PLL cannot lock and mimic the reference signal.

