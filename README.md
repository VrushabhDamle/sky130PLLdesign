# Phase-Locked Loop(PLL) IC design on Open-Source Google-Skywater 130nm Workshop

[![PLL-Workshop-Banner_efabless](https://user-images.githubusercontent.com/89193562/133880800-c6d948ca-9918-4637-bc68-8d563b887694.png)](https://www.vlsisystemdesign.com/pll-design-using-sky130/)

## Brief Description of the Workshop

# *INDEX*
- [Phase-Locked Loop(PLL) IC design on Open-Source Google-Skywater 130nm Workshop](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#phase-locked-looppll-ic-design-on-open-source-google-skywater-130nm-workshop)
    - [Brief Description of the Workshop](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#brief-description-of-the-workshop)
- [INDEX](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#index)
- [Day 1: PLL Theory and Lab setup](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#day-1-pll-theory-and-lab-setup)
    - [Part 1: Introduction to PLL](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-1-introduction-to-pll)
    - [Part 2: Introduction to Phase Frequency Detector](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-2-introduction-to-phase-frequency-detector)
    - [Part 3: Introduction to Charge Pump](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-3-introduction-to-charge-pump)
    - [Part 4: Introduction to Voltage Controlled Oscillator and Frequency Divider](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-4-introduction-to-voltage-controlled-oscillator-and-frequency-divider)
    - [Part 5: Tool Setup and Design Flow](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-5-tool-setup-and-design-flow)
    - [Part 6: Introduction to PDK, specifications and pre-layout circuits](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-6-introduction-to-pdk-specifications-and-pre-layout-circuits)
    - [Part 7: Circuit design simulation tool - Ngspice Setup](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-7-circuit-design-simulation-tool---ngspice-setup)
    - [Part 8: Layout design tool - Magic Setup](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-8-layout-design-tool---magic-setup)

# Day 1: PLL Theory and Lab setup

## Part 1: Introduction to PLL

- To get a precise clock signal without frequency or phase noise and at the same time it has the flexibility of running at a frequency of our choice.
- Two ways in which clock signal can be generated for our application:
    - Quartz crystals
    - Voltage Controlled Oscillators
- Quartz Crysatals have a pure spectrum (there aren't any unwanted frequencies). However, it is designed to give only a certain frequency output and they aren't flexible like the Voltage Controlled Oscillators.
- Voltage Controlled Oscillator can be implemented on chip easily with inverters and the frequency can be controlled with an input voltage. However, they tend to have noise or fluctuations in their phase.
- The purpose of PLL is to make the spectrum of a Voltage Controlled Oscillator pure while still maintaining the flexibility.

![1631964401892](https://user-images.githubusercontent.com/89193562/133887230-40ec071e-a279-4a23-b217-e9e209d9008d.jpg)

- Phase-Locked Loop Intuition:
    - To mimic the reference means to have the same/a multiple of the reference frequency and a constant phase difference with it.

![pll components](https://user-images.githubusercontent.com/89193562/133884254-93e75da1-ff2c-4571-9fcd-d5e26db7a92d.JPG)

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

![state machine format](https://user-images.githubusercontent.com/89193562/133884845-c386f913-15fd-43ed-beeb-6ef34873ab3e.JPG)

- A good way to detect falling or rising edge is by usng a flip flop
- Implementing the circuit with flip flops:
    - The negative edge flip flops are used here. In this case, it is known that if the clock input falls, the flip flop output will go high. This indicates the falling edge.
    - Two flip flops are required because of the need to detect the falling edge of two different signals in different scenarios.
    - Now, from the state diagram, the falling edge of the reference signal arrives and then the falling edge of the output signal arrives. Both up and down signals should now become low. To get this, an additional AND gate is required.

![1631964589994](https://user-images.githubusercontent.com/89193562/133887300-de6788fd-7008-4bda-b21f-5858471ed784.jpg)

- This is one of the boost phase detector circuits.
- There is and issue with the circuit \- **Dead Zone**:
    - Dead Zone prevents us from improving the smallest difference in phase or frequency that the PFD is able to measure.
    - If the signals are very close, then we get an output which is clipped as there isn't enough time for it to rise.
    - A more precise PFD enables better stability for the PLL because it enables minute adjustments of the phase and frequency.

## Part 3: Introduction to Charge Pump

- The role of a CP in PLL is to convert the difference in phase or frequency which is measured digitally into an analog signal that can be used to control the VCO.
- It can be done by using current steering circuits. A current steering circuit steers the current or it directs the current flow from the Vdd to the output or from the output to the ground based on the up or down signal that is provided.
- If up signal is active, the current flows from the Vdd to the output capacitor and charges the output. This increases the voltage at the CP output.
- If down signal is active, the current flows from the output capacitor to the ground and discharges the output. This decreases the voltage at the CP output.
- The reluctance of the capacitor to change voltage quickly, smoothens or averages the voltage change at the output so when the average active time of the up signal is higher than the down signal, the output voltage rises.
- Similarly, when average active time of down signal is higher than the up signal, the output voltage falls.
- Increasing the voltage speeds up the VCO while reduction involtage slows it down.

![1631964721166](https://user-images.githubusercontent.com/89193562/133887355-2c951e28-c412-4be2-a6f9-5c89e568ad53.jpg)

- When the up and down transistors are off, there is still a small current flowing through them in the form of leakage current. This leakage current has a bad impact on output control voltage because it keeps charging the output capacitor even when there is no up or down signal.
- The averaging is still not as smooth as required. There are still fluctuations caused according to the rise and fall of the up and down signals. We can tackle this by replacing the output capacitor with a low pass filter.
- This smoothens out any high frequency fluctuations in the output. LPF has a very significant role in stabilizing the PLL. Without the load filter, the PLL cannot lock and mimic the reference signal.

## Part 4: Introduction to Voltage Controlled Oscillator and Frequency Divider

- Ring Oscillator:
    - It is a sries combination of odd number of inverters which has a certain delay. This causes the output signal to flip after a certain delay.
    - Output period = 2 \* delay(inverter) \* inverter_count
- The frequency depends on delay and delay depends on the current supplied.
- If the current is high, then the output can be charged faster.
- By 'starving' the ring oscillator of current, we can control its frequency.

![1631965316467](https://user-images.githubusercontent.com/89193562/133887593-d39916a3-d885-45d2-95c1-2de570153db5.jpg)

- Frequency divider:
    - The output of a toggle flip flop is half the frequency of the input signal.

![1631965618195](https://user-images.githubusercontent.com/89193562/133887698-ba75fc39-f9f9-456b-bcda-4cd514d360d0.jpg)

- Some Terms:
    - Lock Range: It is the range of frequencies for which the PLL is able to maintain a lock given that it is already in a locked state.
    - Capture Range: It is the range of frequencies for which the PLL is is able to attain a locked stated from an unlocked stated.
    - Settling Time: It is the time within which the PLL is able to attain a lock from an unlocked state.

## Part 5: Tool Setup and Design Flow

- Best to build any software tool from its source code, as it will be the latest version.
- Tools used:
    - Ngspice: It is used for the transistor level circuit simulation
    - Magic: It is used for layout design and parasitic extraction
- In order to install Ngspice, type the following command in the terminal:

    `sudo apt-get install ngspice`
    
- In order to install Magic, follow the given steps:
    - `sudo apt-get update && sudo apt-get upgrade` This step is used to update the OS.
    - `git clone git://opencircuitdesign.com/magic` This step clones the Magic Repository
    - `sudo apt-get install csh` This step installs the csh shell
    - `cd magic` This step is to go into the cloned directory
    - `./configure` This step runs the configure script
    - `make` This step runs the make command to compile
    - `sudo make install` This step installs magic on the device

- Development Flow:

<p align="center">
  <img width="260" height="766" src="https://user-images.githubusercontent.com/89193562/133883982-1d7b74f8-f8fe-493b-8482-2b6473352f5f.JPG">
</p>
    
- It is often the case that after each simulation phase, we would need to make several changes to the circuit to bring it closer to the required specifications.

## Part 6: Introduction to PDK, specifications and pre-layout circuits

- The PDK (Process Design Kit) Content:
    - io: input\-output
    - pr: primitives (spice)
    - sc: standard cell
    - hd: high density
    - hs: high speed
    - lp: low power
    - hdll: high density low leakage
- PDK is provided by the fabrication centres because thats where the transistors get fabricated.
- The characteristics of those transistors in the technology node of interest are available to us through the scripts.
- Other than transistor characteristics, a lot of information is available to help the design process.
- The specifications give the operationg condition at which the PLL has to operate.
- It is based on these specifications, that we will design the circuit.
- We will use the simplified IP specifications from VSD for our PLL design:
    - Corner \- TT
    - Supply \- 1.8V
    - Room Temperature
    - VCO mode and PLL mode
    - Input Fmin = 5MHz and Fmax = 12.5MHz
    - Multiplier \- 8x
    - Jitter (RMS) <~ 20ns
    - Duty Cycle \- 50%
- The first three specifications together are called as PVT corner or Process\-Voltage\-Temperature corner
- Pre\-layout:
    - This phase is all about development and the transistor level simulation of the circuits.
    - In this phase all the circuits are developed in such a way that most of the disadvantages are already overcome.

## Part 7: Circuit design simulation tool - Ngspice Setup

- The first step is to install ngspice using ubuntu's package manager. The command to do so is given above (in [Part 5](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-5-tool-setup-and-design-flow)).
- Next, we have to clone the google skywater pdk. On the terminal type `git clone https://github.com/google/skywater-pdk-libs-sky130_fd_pr.git`
- Now we have to pick the files that we need from "skywater-pdk-libs-sky130_fd_pr" folder
- Go to the cells folder and search nfet and in nfet folder search "nfet_01v8". Again, search "tt" and chose the file named "sky130_fd_pr__nfet_01v8__tt_leak.pm3.spice". Copy this file to the directory that will be used for PLL simulations.
- Go to the cells folder and search pfet and in nfet folder search "pfet_01v8". Again, search "tt" and chose the file named "sky130_fd_pr__pfet_01v8__tt_leak.pm3.spice". Copy this file to the directory that will be used for PLL simulations.
- Go to models and then go to parameters and copy the files "invariant.spice" and "lod.spice" to the directory that will be used for PLL simulations.
- Now in terminal go to the directory that will be used for PLL simulations.
- In the terminal type the command `nano sky130.lib`.
- Now, include all the files that were just copied.
- Save this file using ctrl+s and then exit using ctrl+x.
- The output should look as follows:

![spice lab](https://user-images.githubusercontent.com/89193562/133888591-9b74cff1-7dab-4c95-a342-98465b9c7222.JPG)

- The terminal window should look like:

![terminal-spice](https://user-images.githubusercontent.com/89193562/133888623-02cf8522-57d9-4f1e-be3f-3017d04f0862.JPG)

## Part 8: Layout design tool - Magic Setup

- The first step is to clone the magic repository (given in [Part 5](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-5-tool-setup-and-design-flow))
- Now we have to install the dependancies which can be found at the [Install](http://opencircuitdesign.com/magic/) page
- Now go into the magic folder using the "cd" command and compile magic using `./configur` command.
- Run the configure, make and install commands on the terminal.
- Search open pdks on google and select the [RTimothy/open_pdks](https://github.com/RTimothyEdwards/open_pdks)
- Clone this repository and compile it or download [sky130A.tech](https://drive.google.com/file/d/18BG4zzpRrcHP0UoBcNLA3sWFDVdNlUtp/view) and place it in the main folder.


- **_This is the end of the tasks of the first day._**
