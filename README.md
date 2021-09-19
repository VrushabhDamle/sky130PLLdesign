# Phase-Locked Loop(PLL) IC design on Open-Source Google-Skywater 130nm Workshop

[![PLL-Workshop-Banner_efabless](https://user-images.githubusercontent.com/89193562/133880800-c6d948ca-9918-4637-bc68-8d563b887694.png)](https://www.vlsisystemdesign.com/pll-design-using-sky130/)

## Brief Description of the Workshop

This was a two day workshop conducted by [VLSI System Design]( https://www.vlsisystemdesign.com/) and the topic for the workshop was Phase-Locked Loop(PLL) IC design on Open-Source Google-Skywater 130nm. Over the course of two days this workshop explains the PLL inside out and we also have to design a PLL using certain simulation softwares (ngspice and magic). On the first day of the workshop, we are introduced to PLL and we discuss the circuitry required to design one. We discuss in depth about the individual components used and their role in operating the PLL. We also install the softwares on the first day and this concludes the first day. On the second day of the workshop, we start by preparing spice files and conducting spice simulations of individual components of the PLL. Then using these components, we create a spice file that will work effectively as a complete PLL. After this, we look into the layouts of the individual components and finally combine them to form a final PLL layout. We perform post-layout simulations on the individual components and end the day with discussion on tapeouts and Caravel.

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
- [Day 2: PLL Labs and post-layout simulations](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#day-2-pll-labs-and-post-layout-simulations)
    - [Part 9: PLL components circuit design](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-9-pll-components-circuit-design)
    - [Part 10: PLL components circuit simulations](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-10-pll-components-circuit-simulations)
        - [Simulation File for Charge Pump](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#simulation-file-for-charge-pump)
        - [Simulation File for VCO](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#simulation-file-for-vco)
        - [Simulation File for PFD](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#simulation-file-for-pfd)
        - [For the mcq on charge pump](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#for-the-mcq-on-charge-pump)
    - [Part 11: Steps to combine PLL sub-circuits and PLL full design simulation](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-11-steps-to-combine-pll-sub-circuits-and-pll-full-design-simulation)
    - [Part 12: Troubleshooting steps](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-12-troubleshooting-steps)
    - [Part 13: Layout design](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-13-layout-design)
    - [Part 14: Layout Walkthrough](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-14-layout-walkthrough)
        - [For the mcq on box function](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#for-the-mcq-on-box-function)
    - [Part 15: Parasitic Extraction](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-15-parasitic-extraction)
        - [For the mcq on parasitics extraction](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#for-the-mcq-on-parasitics-extraction)
    - [Part 16: Post Layout simulations](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-16-post-layout-simulations)
        - [The post layout simulation](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#the-post-layout-simulation)
        - [For the mcq on post layout simulation](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#for-the-mcq-on-post-layout-simulation)
    - [Part 17: Steps to combine layouts](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-17-steps-to-combine-layouts)
    - [Part 18: Tapeout theory](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-18-tapeout-theory)
    - [Part 19: Tapeout labs](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-19-tapeout-labs)
- [Conclusion and Opinion](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#conclusion-and-opinion)
- [References](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#references)

# Day 1: PLL Theory and Lab setup

On the first day of the workshop, basic theory of the PLL was taught. The multiple components that the PLL constitutes were discussed in depth and their MOSFET based circuits were seen. The tools that were to be installed were \- Ngspice and Magic. The steps for the installations were told and a walkthrough video was presented if any difficulties were faced. The MOSFET based circuits that were taken were chosen such that they were up-to-date with the latest advancements and minimal disadvantages.

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

![1631981380586](https://user-images.githubusercontent.com/89193562/133895268-b1609619-8ca9-49ac-9345-d2996d100cd1.jpg)

- The reluctance of the capacitor to change voltage quickly, smoothens or averages the voltage change at the output so when the average active time of the up signal is higher than the down signal, the output voltage rises.
- Similarly, when average active time of down signal is higher than the up signal, the output voltage falls.
- Increasing the voltage speeds up the VCO while reduction involtage slows it down.

![1631964721166](https://user-images.githubusercontent.com/89193562/133887355-2c951e28-c412-4be2-a6f9-5c89e568ad53.jpg)

- When the up and down transistors are off, there is still a small current flowing through them in the form of leakage current. This leakage current has a bad impact on output control voltage because it keeps charging the output capacitor even when there is no up or down signal.
- The averaging is still not as smooth as required. There are still fluctuations caused according to the rise and fall of the up and down signals. We can tackle this by replacing the output capacitor with a low pass filter.
- This smoothens out any high frequency fluctuations in the output. LPF has a very significant role in stabilizing the PLL. Without the load filter, the PLL cannot lock and mimic the reference signal.
- There are two thumb rules that one should remember:
    - Cx ~= C/10
    - Loop filter band width ~= (Higher output frequency)/10

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

![2021-09-18 (6)](https://user-images.githubusercontent.com/89193562/133895941-df57a532-dffc-4c5a-ab12-869127bd6e44.png)

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

## Part 8: Layout design tool - Magic Setup

- The first step is to clone the magic repository (given in [Part 5](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-5-tool-setup-and-design-flow))
- Now we have to install the dependancies which can be found at the [Install](http://opencircuitdesign.com/magic/) page
- Now go into the magic folder using the "cd" command and compile magic using `./configur` command.
- Run the configure, make and install commands on the terminal.
- Search open pdks on google and select the [RTimothy/open_pdks](https://github.com/RTimothyEdwards/open_pdks)
- Clone this repository and compile it or download [sky130A.tech](https://drive.google.com/file/d/18BG4zzpRrcHP0UoBcNLA3sWFDVdNlUtp/view) and place it in the main folder.


- \*\***_This is the end of the tasks of the first day._**

# Day 2: PLL Labs and post-layout simulations

On the second day of the workshop, we did a lot of things. Firstly, we performed pre-layout simulations for all the components individually. Then we combined all the files and did a pre-layout spice simulation for the complete PLL. Then we were given a walkthrough of the layout of the PLL. We performed post-layout simulations for the components at this stage and then say the complete layout of the PLL. We created the GDS file for our layout and also saw the further steps required for the tapeout process.

## Part 9: PLL components circuit design

- We created a circuit description ngspice and we did it for the frequency divider circuit.
- A spice file is just a text file with a `.spice` or `.cir` extension.
- To make the file type the following command in the terminal \- `touch FreqDiv.cir`.

![touch_freqDiv](https://user-images.githubusercontent.com/89193562/133896191-6a450561-988b-4509-8450-10ad7a85ec73.JPG)

- Now open the file using the file browser.
- The first line is always given as a comment and we gave the circuit name as the comment.
- Write the following code in the file:

```
*Frequency Divider Circuit

.include sky130nm.lib

xm1 1 2 3 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm2 0 2 3 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm3 3 Clkb 4 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm4 3 Clk 4 0 sky130_fd_pr__nfet_01v8 l=150n w=840n 

xm7 1 4 5 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm8 0 4 5 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm9 5 Clk 6 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm10 5 Clkb 6 0 sky130_fd_pr__nfet_01v8 l=150n w=640n 

xm11 1 6 2 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm12 0 6 2 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm13 1 Clk Clkb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm14 0 Clk Clkb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

v1 1 0 1.8
v2 Clk 0 PULSE 0 1.8 1n 6p 6p 5ns 10ns

c1 6 0 10f
.control
tran 0.1ns 0.2us
plot v(6) v(Clk)+2
.endc

.end
```

- In the command `v2 Clk 0 PULSE 0 1.8 1n 6p 6p 5ns 10ns` the numeric values are placed in the sequence that represents: voltage1, voltage2, delay, rise time, fall time, pulse width, period.
- In the `.control` command the `tran 0.1ns 0.2us` tells the simulator to do a transient analysis with a given sampling rate (here 0.1ns) for a given amount of time (here 0.2us). The `plot v(6) v(Clk)+2` tells it what signals to plot.
- The control block ends with the `.endc` and the spice file ends with `.end`.

## Part 10: PLL components circuit simulations

- In order to simulate the `FreqDiv.cir` file that we have created, first we must enter the directory where the file is saved using the "cd" command.
- To simulate the file type the command `ngspice FreqDiv.cir`

![ngspice_freqDiv](https://user-images.githubusercontent.com/89193562/133914842-a21da9d3-debb-47ce-9699-56807c7a5ad2.JPG)

- The output that we receive is:

![tran_freqDiv](https://user-images.githubusercontent.com/89193562/133914852-a12fc166-99da-4b45-ab75-5fee4def8111.JPG)

- The signals that we wanted are plotted for the amount of time that we have mentioned in the "tran" instruction.
- The frequency divider circuit is working because the output frequency is half of that of the input frequency.
- Spice circuit is similarly created for other circuits and simulation is done for each circuit.

### **Simulation File for Charge Pump**

- First enter the directory in which the `.cir` file is to be created.
- Now type the command \- `touch ChargePump.cir`
- Write the following code in the file:

```
*ChargePump

.include sky130nm.lib

xm43 3 2 1 1 sky130_fd_pr__pfet_01v8 l=150n w=5.4u 
xm44 out downb 3 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm31 out up 7 0 sky130_fd_pr__nfet_01v8 l=150n w=420n
xm32 7 8 0 0 sky130_fd_pr__nfet_01v8 l=150n w=5.4u

xm33 2 2 1 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm34 8 8 0 0 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm35 9 down 3 1 sky130_fd_pr__pfet_01v8 l=150n w=5400n 
xm36 9 9 0 0 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm37 10 10 1 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm38 10 upb 7 0 sky130_fd_pr__nfet_01v8 l=150n w=5400n

xm39 1 down downb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm40 0 down downb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm41 1 up upb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm42 0 up upb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 
v1 1 0 1.8	
v2 up 0 0
*PULSE 0 1.8 1n 6p 6p 100ns 200ns
v3 down 0 0

r1 out rc 200
c1 rc 0 64f
c2 out 0 10f

.ic v(out) = 0
.ic c(out) = 0
.control
tran 1ns 1us
plot v(out) C(out)
*plot v(6) V(Clk)+2
* v(D) v(Clk) v(6)
.endc
```

- `.ic` command is used to specify the initial conditions of a signal.
- Here it is done to specify the initial condition, before the charging or discharging that happens in the charge pump.
- V2 voltage source is specified as the up signal with 0V and V3 voltage source is specified as the down signal with 0V.
- This enables us to see if there is any leakage happening when no input is given.
- In order to simulate the `ChargePump.cir` file that we have created, first we must enter the directory where the file is saved using the "cd" command.
- To simulate the file type the command `ngspice ChargePump.cir`

![ngspice_chargePump](https://user-images.githubusercontent.com/89193562/133915319-c20caefd-7922-41a9-9369-38ae8498f570.JPG)

- The output looks like:

![tran_chargePump](https://user-images.githubusercontent.com/89193562/133915324-df5bf808-636b-46a0-a3f5-478a7d17ee73.JPG)

- We can see that current leakage is very small for this charge pump.
- It is just around 40uV when simulated for 1us.
- The slope indicates the charging happening when up and down signals are given 0V.
- Now we will give an actual pulse signal and see the response.
- To do so do, first look for V2 in the file "ChargePump.cir":
```
v2 up 0 0
*PULSE 0 1.8 1n 6p 6p 100ns 200ns
```
- Now change it to `v2 up 0 PULSE 0 1.8 1n 6p 6p 100ns 200ns`. Also change the tran instruction from `tran 1ns 1us` to `tran 1ns 20us`.
- This means that we are giving a pulse to the "up signal" and thus the graph should rise up.
- In order to simulate the `ChargePump.cir` file that we have created, first we must enter the directory where the file is saved using the "cd" command.
- To simulate the file type the command `ngspice ChargePump.cir`

![ngspice_chargePump](https://user-images.githubusercontent.com/89193562/133915319-c20caefd-7922-41a9-9369-38ae8498f570.JPG)

- This time the output is a little different as it should be and it looks like:

![tran_chargePump_v2PULSE](https://user-images.githubusercontent.com/89193562/133915536-56892842-88e4-463f-9c7c-37e36f390aaa.JPG)


### **Simulation File for VCO**

- Now, we will create a ".cir" file for a VCO.
- First enter the directory in which the `.cir` file is to be created.
- Now type the command \- `touch VCO.cir`
- Write the following code in the file:

```
*Current starved 3 stage VCO
.include sky130nm.lib

xm1 10 16 3 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm2 3 16 9 9  sky130_fd_pr__nfet_01v8 l=150n w=420n

xm3 10 3 4 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm4 4 3 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm5 10 4 12 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm6 12 4 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm11 10 12 13 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm12 13 12 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm13 10 13 14 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm14 14 13 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm15 10 14 15 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm16 15 14 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm17 10 15 16 10 sky130_fd_pr__pfet_01v8 l=150n w=2400n
xm18 16 15 9 9 sky130_fd_pr__nfet_01v8 l=150n w=1200n

xm7 10 5 1 1 sky130_fd_pr__pfet_01v8 l=150n w=1080n
xm8 5 5 1 1 sky130_fd_pr__pfet_01v8 l=150n w=840n
xm9 5 in 0 0 sky130_fd_pr__nfet_01v8 l=150n w=840n
xm10 9 in 0 0 sky130_fd_pr__nfet_01v8 l=150n w=1080n

xm19 1 16 11 1 sky130_fd_pr__pfet_01v8 l=150n w=1080n
xm20 11 16 0 0 sky130_fd_pr__nfet_01v8 l=150n w=540n

*c1 11 0 10f
v1 1 0 1.8
v2 in 0 0.6


.control
tran 0.1ns 0.5us
plot v(in) v(11)
*setplot tran1
*linearize v(14)
*set specwindow=blackman
*fft v(14)
*dc v2 0 1.2 0.01
*plot mag(v(14))
.endc
.end
```

- Here the input control signal is given by V2 source.
- By adjusting this control voltage we can observe whether for a particular frequency range this VCO will be able to produce usable oscillations.
- In order to simulate the `VCO.cir` file that we have created, first we must enter the directory where the file is saved using the "cd" command.
- To simulate the file type the command `ngspice VCO.cir`

![ngspice_vco](https://user-images.githubusercontent.com/89193562/133915670-8a77a6c0-896e-4d3d-af2a-97e20350cf9a.JPG)

- The output that we receive is:

![tran_vco](https://user-images.githubusercontent.com/89193562/133915673-2f72c731-eae9-4015-9bd2-47b329392967.JPG)

- In the above image we are getting proper oscillations.
- These oscillations are full swing because we have kept one extra inverter at the output.
- Otherwise, these oscillations will be of lower and varying amplitude.

### **Simulation File for PFD**

- Now, we will create a ".cir" file for a PFD.
- First enter the directory in which the `.cir` file is to be created.
- Now type the command \- `touch PFD.cir`
- Write the following code in the file:

```
*PD_10T
.include sky130nm.lib

xm1 1 clk1 3 1 sky130_fd_pr__pfet_01v8 l=150n w=640n 
xm2 3 clk1 4 0 sky130_fd_pr__nfet_01v8 l=150n w=1800n
xm3 4 clk2 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm4 1 clk2 6 1 sky130_fd_pr__pfet_01v8 l=150n w=640n 
xm5 6 clk2 7 0 sky130_fd_pr__nfet_01v8 l=150n w=1800n
xm6 7 clk1 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm7 8 clk1 3 0 sky130_fd_pr__nfet_01v8 l=150n w=840n 
xm8 clk1 clk1 8 1 sky130_fd_pr__pfet_01v8 l=150n w=640n

xm11 upb 8 1 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm12 upb 8 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm15 up upb 1 1 sky130_fd_pr__pfet_01v8 l=150n w=960n
xm16 up upb 0 0 sky130_fd_pr__nfet_01v8 l=150n w=480n
  
xm9 9 clk2 6 0 sky130_fd_pr__nfet_01v8 l=150n w=840n
xm10 clk2 clk2 9 1 sky130_fd_pr__pfet_01v8 l=150n w=640n

xm13 downb 9 1 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm14 downb 9 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm17 down downb 1 1 sky130_fd_pr__pfet_01v8 l=150n w=960n
xm18 down downb 0 0 sky130_fd_pr__nfet_01v8 l=150n w=480n


*output cap
c1 up 0 3f
c2 down 0 3f

*sources
v1 1 0 1.8v
v2 clk1 0 pulse(0 1.8 0 6p 6p 5ns 10ns)
v3 clk2 0 pulse(0 1.8 6ns 6p 6p 5ns 10ns) 

*simulation
.control
tran 10ns 800ns 120ns
plot v(clk2)+4 v(clk1)+4 v(up)+2 v(down)
.endc
.end
```

- Here v2 and v3 are given as the two input clock signals of phase difference 6ns.
- In order to simulate the `PDF.cir` file that we have created, first we must enter the directory where the file is saved using the "cd" command.
- To simulate the file type the command `ngspice PDF.cir`

![ngspice_pfd](https://user-images.githubusercontent.com/89193562/133915847-17aef0c0-a7c6-4275-805c-7580a35606ae.JPG)

- The output of the simulation looks like:

![tran_pfd](https://user-images.githubusercontent.com/89193562/133915854-4539f216-9a41-49ef-a5dc-bc69953e11a2.JPG)

- We can zoom the output to get a better view by right clicking and dragging it over the area that we wish to select.
- This looks like:

![tran_pfd_zoomed](https://user-images.githubusercontent.com/89193562/133915866-f9b0ee7f-8d49-458f-b265-092d9b550070.JPG)

- We can see how the circuit is able to detect the slight difference in the phase.

### **For the mcq on charge pump**

- In the file "ChargePump.cir" find the tran instruction.
- Change the tran instruction from `tran 1ns 1us` to `tran 1ns 20us`
- In order to simulate the `ChargePump.cir` file that we have created, first we must enter the directory where the file is saved using the "cd" command.
- To simulate the file type the command `ngspice ChargePump.cir`

![ngspice_chargePump](https://user-images.githubusercontent.com/89193562/133915939-1498b997-c967-4a5e-8b22-30a1b57132db.JPG)

- The output is:

![tran_chargePump_20us](https://user-images.githubusercontent.com/89193562/133915963-e9584062-91d9-4cad-a270-903c5cd5f72d.JPG)

- From the above snap shot the capacitor is charged upto a voltage of 800uV when the simulation is run for 20us.

## Part 11: Steps to combine PLL sub-circuits and PLL full design simulation

- We need to make a PLL. For this we combine the circuits that we have observed so far in a single file using the subcircuit block in spice.
- The combined file is:

```
*PLL
.include sky130nm.lib

xx1 Clk_Ref Clk_Out_by_8 up down pd
xx2 up down VCtrl cp

*Loop Filter
r1 VCtrl rc1 490
c1 rc1 0 355f
r2 rc1 rc2 490
c2 rc2 0 350f
r3 rc2 rc3 490
c3 rc3 0 345f

xx3 rc3 Clk_Out vco

xx4 Clk_Out Clk_Out_by_2 fd
xx5 Clk_Out_by_2 Clk_Out_by_4 fd
xx6 Clk_Out_by_4 Clk_Out_by_8 fd

v1 Clk_Ref 0 PULSE 0 1.8 0 6ps 6ps 40ns 80ns

.ic v(VCtrl) = 0
.ic v(Clk_Out_by_2) = 0
.ic v(Clk_Out_by_4) = 1.8
.ic v(Clk_Out_by_8) = 0
.control
tran 0.1ns 180us
plot v(Clk_Ref) v(Clk_Out_by_8) v(Clk_Out_by_4)+2 v(Clk_Out_by_2)+4 v(Clk_Out)+6 v(up)+8 v(down)+10 v(VCtrl)+12
.endc

*PFD
.subckt pd Clk1 Clk2 up down 
xm1 1 clk1 3 1 sky130_fd_pr__pfet_01v8 l=150n w=640n 
xm2 3 clk1 4 0 sky130_fd_pr__nfet_01v8 l=150n w=1800n
xm3 4 clk2 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm4 1 clk2 6 1 sky130_fd_pr__pfet_01v8 l=150n w=640n 
xm5 6 clk2 7 0 sky130_fd_pr__nfet_01v8 l=150n w=1800n
xm6 7 clk1 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm7 8 clk1 3 0 sky130_fd_pr__nfet_01v8 l=150n w=2400n 
xm8 clk1 clk1 8 1 sky130_fd_pr__pfet_01v8 l=150n w=640n

xm11 upb 8 1 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm12 upb 8 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm15 up upb 1 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm16 up upb 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n
  
xm9 9 clk2 6 0 sky130_fd_pr__nfet_01v8 l=150n w=2400n
xm10 clk2 clk2 9 1 sky130_fd_pr__pfet_01v8 l=150n w=640n

xm13 downb 9 1 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm14 downb 9 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm17 down downb 1 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm18 down downb 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n


*output cap
*c1 up 0 6f
*c2 down 0 6f

v1 1 0 1.8
.ends pd


*CP
.subckt cp up down out
xm43 3 2 1 1 sky130_fd_pr__pfet_01v8 l=150n w=18u 
xm44 out downb 3 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm31 out up 7 0 sky130_fd_pr__nfet_01v8 l=150n w=420n
xm32 7 8 0 0 sky130_fd_pr__nfet_01v8 l=150n w=4.8u

xm33 2 2 1 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm34 8 8 0 0 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm35 9 down 3 1 sky130_fd_pr__pfet_01v8 l=150n w=5400n 
xm36 9 9 0 0 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm37 10 10 1 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm38 10 upb 7 0 sky130_fd_pr__nfet_01v8 l=150n w=5400n

xm39 1 down downb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm40 0 down downb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm41 1 up upb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm42 0 up upb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

*r1 out rc 200
*c1 rc 0 8f

v1 1 0 1.8
.ends cp


*VCO
.subckt vco in 17
xm1 10 16 3 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm2 3 16 9 9  sky130_fd_pr__nfet_01v8 l=150n w=420n

xm3 10 3 4 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm4 4 3 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm5 10 4 12 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm6 12 4 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm11 10 12 13 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm12 13 12 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm13 10 13 14 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm14 14 13 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm15 10 14 15 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm16 15 14 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm17 10 15 16 10 sky130_fd_pr__pfet_01v8 l=150n w=2400n
xm18 16 15 9 9 sky130_fd_pr__nfet_01v8 l=150n w=1200n

xm7 10 5 1 1 sky130_fd_pr__pfet_01v8 l=150n w=1080n
xm8 5 5 1 1 sky130_fd_pr__pfet_01v8 l=150n w=840n
xm9 5 in 0 0 sky130_fd_pr__nfet_01v8 l=150n w=840n
xm10 9 in 0 0 sky130_fd_pr__nfet_01v8 l=150n w=1080n

xm19 1 16 11 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm20 11 16 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm21 1 11 17 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm22 17 11 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

*c1 11 0 24f
v1 1 0 1.8
.ends vco


*FD
.subckt fd Clk 10

xm1 1 2 3 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm2 0 2 3 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm3 3 Clkb 4 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm4 3 Clk 4 0 sky130_fd_pr__nfet_01v8 l=150n w=840n 

xm7 1 4 5 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm8 0 4 5 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm9 5 Clk 6 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm10 5 Clkb 6 0 sky130_fd_pr__nfet_01v8 l=150n w=640n 

xm11 1 6 2 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm12 0 6 2 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm13 1 Clk Clkb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm14 0 Clk Clkb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm15 7 6 1 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm16 7 6 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm19 1 7 10 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm20 10 7 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 


*c1 7 0 18f
v1 1 0 1.8
.ends fd
```

- If we notice the CP circuit, it is just pasted in the sub-circuit block and it ends with a `.ends cp` statement.
- The subcircuit for CP is defined as `.subckt cp up down out`. It is basically giving a name to the block and then specifying the input-output pins.
- To instantiate a sub-circuit, we use "xx" which means that it is a sub-circuit of general type.
- In instantiation, we mention the sub-circuit name last while during the definition, sub-circuit name is given first and then the pin names are given.
- Similar to the way we instantiated the CP sub-circuit, we have instantiated all circuits and added the loop filter as well.
- We have kept V1 voltage pulse as input reference signal and the period of this signal is "80ns" meaning that it is a 12.5MHz signal.
- Proper naming of the nets and proper assignment of the values for each parameter like width, length, etc. is important as one wrong naming will cause an error in the spice simulation.
- Now we will simulate the combined pll file using the "ngspice" command as shown below:

![ngspice_pll_combined](https://user-images.githubusercontent.com/89193562/133916522-e82dc472-ce7c-441a-866a-9aa31f63243b.JPG)

- The output that we receive is:

![tran_pll](https://user-images.githubusercontent.com/89193562/133917203-915d78fb-8462-44f5-83a7-77d63bb18109.JPG)

- The very first row is the CP output which is the control voltage that goes to the VCO is displayed.
- Right below it are the up and down signals.
- Then come the output signals and the signals divided by 2 and by 4.
- Finally and most importantly, come the last two signals which are the reference signal in red and the signal divided by 8 in blue. These signals are overlapping.

- Let's zoom into an area by right clicking and dragging the cursor:

![tran_pll_zoom](https://user-images.githubusercontent.com/89193562/133917206-b0296225-8f8b-4f62-8167-4767bf3a550f.JPG)

- Here we can see how the up and down signals are coming into play and we see the frequency division happening across the fourth, fifth, and the sixth rows.
- The charge pump output seems constant but actually, it is fluctuating very slightly based on the up and down signals.
- Most importantly, if we zoom in at the bottom, we can the the difference between the reference signal in red and the output frequency divided by 8 signal as shown below:

![tran_pll_zoom_even_more](https://user-images.githubusercontent.com/89193562/133917209-ba4a9b3b-b137-4296-91b6-c32404c5485d.JPG)

- This difference in output signal divided by 8 and the reference signal is the phase noise of this PLL that we created.
- If the PLL becomes perfect, which is an ideal case, then the blue feedback signal will overlap the red reference signal perfectly which is what we wish for.
- If we take the root-mean-square (RMS) of the variation of the output signal, we get the Jitter (RMS) value which denotes the phase noise.
- It is important to note that this blue signal is in-fact created by the VCO.

## Part 12: Troubleshooting steps

- Observe what kind of issue is faced.
- Always debug individual components fully before moving to the combined simulation.
- Check if any signals are coming flat or if the simulation is crashing. If this is the case then check if all the connections are done properly. Also check if there are any issues like wrong naming, capitalization issues or parameter value issues.
- If the signals are right but the mimicking is not happening then verify the following:
    - For what range of frequencies is the VCO working properly: Is our required output frequency range lying in the VCO's working range.
    - Is the Phase Frequency Detector able to detect the differences: If the phase difference is very small, the PFD might not be able to detect it.
    - Is the rate of Charge Pump output charging and discharging fast: Is it too fast or too slow? Is there too much fluctuations in charging or discharging? This means that the transistor sizing is the thing to pay attention to. Check the response of the CP when 0V is given as the input. If it is still charging then the charge leakage is the issue.
    - Whether the loop filter values are working out: This can be found out using the thumb rules (in [Part 3](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-3-introduction-to-charge-pump)

## Part 13: Layout design

- To open magic first enter the directory containing the "sky130A.tech" file using the "cd" commands.
- Type `magic -T sky130A.tech` in the terminal window.
- Two files should now open up as follows:

![magic_view](https://user-images.githubusercontent.com/89193562/133918277-5ea0d518-950c-4d6a-bdfe-8c31a47d9344.JPG)
![magic_command_window_view](https://user-images.githubusercontent.com/89193562/133918280-e9023432-a6af-41a0-b6fd-88327fe3ab7c.JPG)

- The way to draw here in magic is first to make a box and then fill it with a material.
- By left clicking, we fix the left bottom corner of the box.
- By right clicking, we fix the right top corner of the box.
- If we hover upon a layer (layers panel is present on the right hand side of the window), we can see the name of the layer on the top right corner of the screen.
- By middle clicking on a layer, the box gets filled by the selected layer.
- Materials needed for the transistors:
    - P-diffusion for the PMOS and N-diffusion for the NMOS.
    - For the gate, polysilicon layer is needed.
- DRC error means that there is a size issue or a closeness issue. To know what exactly the issue is, select some part of the error region and press the "?" button on the keyboard and then the error will show up on the "magic command window".
- Before creating a PMOS, we must create an N-Well region and then place the PMOS over it.
- To copy a transistor, make a box around the transistor and press "A" button on the keyboard. Now, place the cursor where we wish to copy it and press "C" button. If we press the "M" button then it becomes the move operation.
- For placing Vdd and ground, place the metal1 layer.
- To connect two transistors, use the loacal interconnect layer (locali) like a wire.
- To connect two layers, look for contact layers in the tray. They are represented with a cross symbol.
- As long as we do not connect a contact, two different layers will not touch even if they overlap.
- If we get a DRC error at this point it means that either the size of the contact is too small or the region of metal1 and local interconnect around the contact is not enough.
- To create a label, draw a line around the edge of the layer that we want to label. A line is drawn by making a box of zero thickness. Type the command `label name` in the magic command window. Name can be any name to be used as label.
- To make a port, draw a box around the label and type `port make` in the magic command window.
- We need to make ports because when we extract the parasitics from our design, the input and output ports will automatically have these names as we have labelled them as ports.

## Part 14: Layout Walkthrough

- We saw the previously designed magic files of the following circuits:
    - Frequency Divider
    - Phase Frequency Detector
        - In the PFD design, on the right side, there are two similar drawings on the top and on the bottom.
        - They are additional buffers that were kept for getting full swing.
    - Charge Pump
        - Top most long transistor is just for enabling or disabling the charge pump.
        - Right below it is the upper current source. This much difference in the size of the transistor for the current source is to allow maximum current for the charging and discharging process.
        - Two inverters on the left create the UPz and the DOWNz signals (UPz = up bar and DOWNz = down bar or their inverted variants).
    - Voltage Controlled Oscillator
        - There are seven inverters to reduce the range of frequencies that we are dealing with.
        - Only the last inverter in the inverter is large to improve the driving strength of the oscillator.
        - There is an additional inverter at the end and its purpose is to obtain a full swing for the output.
        - At the top there is a small PMOS that acts as an enable or disable for the VCO.

### For the mcq on box function

- First copy the "FD.mag" file in the directory where the technology file "sky130A.tech" is placed.
- Through the terminal enter the directory refered above using the "cd" command.
- Type the command `magic -T sky130A.tech FD.mag` in the terminal.
- Now the magic file should open and it should look like:

![magic_output_fdmag](https://user-images.githubusercontent.com/89193562/133922745-602824ae-cddb-460b-b66a-0db4facf75a2.JPG)

- Now select the entire are of the layout by using left-click and right-click.
- On the magic command window type the command `box`
- This should give an output as follows:

![magic_command_window_fdmag](https://user-images.githubusercontent.com/89193562/133922786-26ced722-b1e3-482f-8485-1d964949eecc.JPG)

- The area in sq. um is given as 29.82 and hence it is the answer.

## Part 15: Parasitic Extraction

In order to do the parasitics extraction follow the steps given below:
- Open the magic file of the circuit that is to be extracted.
- Press "I" button on the keyboard. It selects the whole design.
- In the magic command window type `extract all`. This extracts the layout connectivity information into a ".ext" file.
- Generally, if there are any warnings at this point, they would be because of wrong connections or short circuits or etc. But these are warnings and need not be errors.
- Now, we need to convert the ".ext" file to a ".spice" file to use for simulations.
- In the magic command window type `ext2spice cthresh 0 rthresh 0` and then type `ext2spice`.
- Here the cthreshold 0 and rthreshold 0 setting is given to tell magic that if any amount of capacitive or resistive effect is present, then we want to extract it.
- In the spice we find a `.option scale=10000u`. Every parameter in the spice file is multiplies by this scale.
- For our case, since we know that the scaling factor is 10n so change the .option command from scale=10000u to scale=10n.

### For the mcq on parasitics extraction

- First copy the "FD.mag" file in the directory where the technology file "sky130A.tech" is placed.
- Through the terminal enter the directory refered above using the "cd" command.
- Type the command `magic -T sky130A.tech FD.mag` in the terminal.
- Now the magic file should open. When it opens press the "I" button on the keyboard and then the design will look like:

![magic_fdmag_parasitics](https://user-images.githubusercontent.com/89193562/133924023-74cc7432-1066-41e0-b6e6-682996e7f185.JPG)

- Now in the magic command window, type the commands required to extract the parasitics as discussed above. The magic command window shall look like:

![magic_command_window_fdmag_parasitics](https://user-images.githubusercontent.com/89193562/133924070-5769c25f-5d09-4b77-86e0-7afe1fa09724.JPG)

- Now open the "FD.spice" file that is created. We observe that there are capacitors from C0 to C42 so there are a total of 43 capacitors present and hence it is the answer.

## Part 16: Post Layout simulations

- First extract the spice file from the "PFD.mag" file (as done in [Part 15](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-15-parasitic-extraction))
- Now using the terminal enter the directory where "sky130nm.lib" and "PFD.spice" are saved using the "cd" command.
- Type the command `nano PFD_postlay.cir` in the terminal as shown:

![pfd_postlay_cir](https://user-images.githubusercontent.com/89193562/133925440-d46c9af4-8bf0-4e93-a5e4-d47ec128b5a4.JPG)

- In the file created type the code:

```
.include sky130nm.lib
.include PFD.spice

xx1 Ref_Clk Up Down Clk2 GND VCC PFD

v1 VDD GND 1.8v

v2 Ref_Clk GND PULSE 0 1.8v 0 6p 6p 40n 80n

v3 Clk2 GND PULSE 0 1.8v 10n 6p 6p 40n 80n

.control 
tran 0.1n 5u
plot v(Up) v(Down)+2 v(Ref_Clk)+4 v(Clk2)+6
.endc

.end
```

- In the terminal, it looks like:

![pfd_postlay_cir_file](https://user-images.githubusercontent.com/89193562/133925641-a2b8458f-95c1-4017-aff8-4df1927090b3.JPG)

- Now save this file using the ctrl+S command and exit it using the ctrl+X command.
- Run this file using ngspice as shown:

![pfd_postlay_cir_tran](https://user-images.githubusercontent.com/89193562/133925640-cb21aa30-8310-469f-9961-095db3576a47.JPG)

- The zoomed version of the output looks like:

![pfd_postlay_cir_tran_zoom](https://user-images.githubusercontent.com/89193562/133925687-40a9db94-2957-42a7-8d8b-1cd0815d1c50.JPG)

- Now we will simulate it for a phase difference between Ref_Clk and Clk2 to be 1ns.
- To do so change the line from `v3 Clk2 GND PULSE 0 1.8v 10n 6p 6p 40n 80n` to `v3 Clk2 GND PULSE 0 1.8v 1n 6p 6p 40n 80n`
- After doing this the file, opened in terminal should look like:

![pfd_postlay_cir_file_small_phase](https://user-images.githubusercontent.com/89193562/133925774-081caa68-0d1e-4460-aae6-e0617b75015e.JPG)

- The output now looks like:

![pfd_postlay_cir_tran_small_phase](https://user-images.githubusercontent.com/89193562/133925830-478a30ac-39cf-4bc2-b5c7-a62f4f69347a.JPG)

- The zoomed output looks like:

![pfd_postlay_cir_tran_small_phase_zoom](https://user-images.githubusercontent.com/89193562/133925837-10454fcc-7176-4f51-83be-1f47da783b27.JPG)

- So, the phase difference of even 1ns is detected.
- This performance is possible because of the circuit that we have chosen for the PFD.
- The default circuit that was discussed in the theory has the dead zone issue which doesn't allow the detection of such narrow phase differences.

### **The post layout simulation**

- To simulate the circuit after layout we need to write the following code in the file "PLL_PostLay.cir":

```
*PLL
.include sky130nm.lib
.option scale = 0.01u
xx1 Clk_Ref Clk_Out_by_8 up down pd
xx2 up down VCtrl cp

*Loop Filter
r1 VCtrl rc1 490
c1 rc1 0 215f
r2 rc1 rc2 490
c2 rc2 0 210f
r3 rc2 rc3 490
c3 rc3 0 205f

xx3 rc3 Clk_Out vco

xx4 Clk_Out Clk_Out_by_2 fd
xx5 Clk_Out_by_2 Clk_Out_by_4 fd
xx6 Clk_Out_by_4 Clk_Out_by_8 fd

v1 Clk_Ref 0 PULSE 0 1.8 0 6ps 6ps 40ns 80ns

.ic v(VCtrl) = 0
.ic v(Clk_Out_by_2) = 0
.ic v(Clk_Out_by_4) = 1.8
.ic v(Clk_Out_by_8) = 0
.control
tran 0.1ns 180us
plot v(Clk_Ref) v(Clk_Out_by_8) v(Clk_Out_by_4)+2 v(Clk_Out_by_2)+4 v(Clk_Out)+6 v(up)+8 v(down)+10 v(VCtrl)+12
plot v(Clk_Ref) v(Clk_Out_by_8)+2
.endc

*PFD
.subckt pd Clk_Ref Clk2 Up Down 
XM1000 VDD a_7_412# a_460_368# VDD sky130_fd_pr__pfet_01v8 w=72 l=15
+  ad=1664.03 pd=142.146 as=2232 ps=206
XM1001 GND a_7_412# a_460_368# GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=842.4 pd=91.8 as=1116 ps=134
XM1002 a_264_92# Clk2 a_208_92# GND sky130_fd_pr__nfet_01v8 w=240 l=15
+  ad=7920 pd=546 as=5314.29 ps=321.143
XM1003 VDD Clk2 a_208_92# VDD sky130_fd_pr__pfet_01v8 w=65 l=15
+  ad=1502.25 pd=128.326 as=2145 ps=196
XM1004 Up a_460_368# GND GND sky130_fd_pr__nfet_01v8 w=48 l=15
+  ad=1392 pd=154 as=1123.2 ps=122.4
XM1005 GND a_264_92# a_485_83# GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=842.4 pd=91.8 as=1116 ps=134
XM1006 a_151_92# Clk_Ref GND GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=1044 pd=74 as=842.4 ps=91.8
XM1007 VDD a_264_92# a_485_83# VDD sky130_fd_pr__pfet_01v8 w=72 l=15
+  ad=1664.03 pd=142.146 as=2232 ps=206
XM1008 Down a_485_83# VDD VDD sky130_fd_pr__pfet_01v8 w=96 l=15
+  ad=2880 pd=252 as=2218.71 ps=189.528
XM1009 a_7_412# Clk_Ref a_7_356# GND sky130_fd_pr__nfet_01v8 w=240 l=15
+  ad=7920 pd=546 as=5314.29 ps=321.143
XM1010 Up a_460_368# VDD VDD sky130_fd_pr__pfet_01v8 w=96 l=15
+  ad=2880 pd=252 as=2218.71 ps=189.528
XM1011 VDD Clk_Ref a_7_356# VDD sky130_fd_pr__pfet_01v8 w=65 l=15
+  ad=1502.25 pd=128.326 as=2145 ps=196
XM1012 Down a_485_83# GND GND sky130_fd_pr__nfet_01v8 w=48 l=15
+  ad=1392 pd=154 as=1123.2 ps=122.4
XM1013 Clk_Ref Clk_Ref a_7_412# VDD sky130_fd_pr__pfet_01v8 w=65 l=15
+  ad=2145 pd=196 as=2145 ps=196
XM1014 a_7_299# Clk2 GND GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=1044 pd=74 as=842.4 ps=91.8
XM1015 a_208_92# Clk2 a_151_92# GND sky130_fd_pr__nfet_01v8 w=180 l=15
+  ad=3985.71 pd=240.857 as=5220 ps=370
XM1016 Clk2 Clk2 a_264_92# VDD sky130_fd_pr__pfet_01v8 w=65 l=15
+  ad=2145 pd=196 as=2145 ps=196
XM1017 a_7_356# Clk_Ref a_7_299# GND sky130_fd_pr__nfet_01v8 w=180 l=15
+  ad=3985.71 pd=240.857 as=5220 ps=370
C0 Down Up 0.00fF
C1 a_264_92# VDD 0.13fF
C2 a_208_92# a_485_83# 0.02fF
C3 a_460_368# Clk_Ref 0.00fF
C4 Clk2 a_485_83# 0.06fF
C5 a_7_412# VDD 0.14fF
C6 Up VDD 0.13fF
C7 a_460_368# a_485_83# 0.01fF
C8 Down VDD 0.56fF
C9 a_264_92# a_208_92# 0.49fF
C10 a_264_92# Clk2 0.27fF
C11 a_264_92# Clk_Ref 0.01fF
C12 a_7_412# a_208_92# 0.01fF
C13 a_7_412# Clk2 0.01fF
C14 a_7_412# Clk_Ref 0.19fF
C15 a_264_92# a_460_368# 0.00fF
C16 a_7_412# a_7_356# 0.49fF
C17 a_264_92# a_485_83# 0.37fF
C18 a_7_412# a_460_368# 0.34fF
C19 Down Clk2 0.02fF
C20 a_7_412# a_485_83# 0.00fF
C21 a_460_368# Up 0.16fF
C22 Up a_485_83# 0.00fF
C23 a_208_92# VDD 0.27fF
C24 Clk2 VDD 0.08fF
C25 VDD Clk_Ref 0.20fF
C26 Down a_485_83# 0.16fF
C27 a_7_356# VDD 0.15fF
C28 a_7_412# a_264_92# 0.03fF
C29 a_460_368# VDD 0.20fF
C30 VDD a_485_83# 0.31fF
C31 a_208_92# Clk2 0.05fF
C32 a_208_92# Clk_Ref 0.01fF
C33 a_7_412# Up 0.01fF
C34 Clk2 Clk_Ref 0.11fF
C35 Down a_264_92# 0.01fF
C36 a_7_356# a_208_92# 0.02fF
C37 a_7_356# Clk2 0.01fF
C38 a_7_356# Clk_Ref 0.10fF
C39 Up GND 0.22fF
C40 VDD GND 4.13fF
C41 a_485_83# GND 0.34fF
C42 a_264_92# GND 0.52fF
C43 a_208_92# GND 0.10fF
C44 a_7_356# GND 0.34fF
C45 a_460_368# GND 0.34fF
C46 a_7_412# GND 0.65fF


*output cap
*c1 up 0 6f
*c2 down 0 6f

v1 VDD GND 1.8
.ends pd


*CP
.subckt cp Up Down Out
XM1000 a_174_531# a_127_486# a_248_475# VDD sky130_fd_pr__pfet_01v8 w=1800 l=15
+  ad=59400 pd=3728.85 as=47294.2 ps=2895.72
XM1001 GND a_340_202# a_462_191# GND sky130_fd_pr__nfet_01v8 w=480 l=15
+  ad=15785.8 pd=1205.27 as=10416.3 ps=592.994
XM1002 a_248_475# a_134_73# Out VDD sky130_fd_pr__pfet_01v8 w=42 l=15
+  ad=1103.53 pd=67.5667 as=1386 ps=150
XM1003 a_134_73# Down GND GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=1188 pd=138 as=1183.94 ps=90.395
XM1004 VDD ENb a_31_494# VDD sky130_fd_pr__pfet_01v8 w=60 l=15
+  ad=2023.9 pd=185.854 as=2340 ps=198
XM1005 a_248_475# Down a_248_427# VDD sky130_fd_pr__pfet_01v8 w=540 l=15
+  ad=14188.3 pd=868.715 as=17820 ps=1146
XM1006 a_258_74# Up GND GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=1188 pd=138 as=1183.94 ps=90.395
XM1007 GND a_340_202# a_340_202# GND sky130_fd_pr__nfet_01v8 w=44 l=15
+  ad=1447.03 pd=110.483 as=1452 ps=154
XM1008 a_462_143# a_462_143# VDD VDD sky130_fd_pr__pfet_01v8 w=42 l=15
+  ad=1386 pd=150 as=1416.73 ps=130.098
XM1009 a_174_531# a_127_486# a_127_486# VDD sky130_fd_pr__pfet_01v8 w=44 l=15
+  ad=1452 pd=91.1497 as=1452 ps=154
XM1010 Out Up a_462_191# GND sky130_fd_pr__nfet_01v8 w=42 l=15
+  ad=1386 pd=150 as=911.424 ps=51.887
XM1011 a_248_427# a_248_427# GND GND sky130_fd_pr__nfet_01v8 w=42 l=15
+  ad=1386 pd=150 as=1381.26 ps=105.461
XM1012 a_462_191# a_258_74# a_462_143# GND sky130_fd_pr__nfet_01v8 w=540 l=15
+  ad=11718.3 pd=667.119 as=17820 ps=1146
XM1013 a_258_74# Up VDD VDD sky130_fd_pr__pfet_01v8 w=72 l=15
+  ad=2376 pd=210 as=2428.68 ps=223.024
XM1014 a_134_73# Down VDD VDD sky130_fd_pr__pfet_01v8 w=72 l=15
+  ad=2376 pd=210 as=2428.68 ps=223.024
C0 a_258_74# VDD 0.18fF
C1 VDD Up 0.21fF
C2 a_248_427# Out 0.00fF
C3 a_258_74# Up 0.09fF
C4 a_462_191# a_340_202# 0.01fF
C5 a_134_73# Down 0.12fF
C6 Down ENb 0.00fF
C7 a_462_191# a_462_143# 0.72fF
C8 a_134_73# VDD 0.16fF
C9 a_248_475# a_248_427# 0.58fF
C10 VDD ENb 0.01fF
C11 a_174_531# a_248_427# 0.25fF
C12 a_134_73# a_258_74# 0.05fF
C13 a_134_73# Up 0.41fF
C14 VDD Out 1.29fF
C15 a_462_191# a_248_427# 0.02fF
C16 a_127_486# Down 0.03fF
C17 a_462_143# a_248_427# 0.01fF
C18 Out Up 0.03fF
C19 a_127_486# VDD 0.05fF
C20 a_174_531# Down 0.02fF
C21 a_248_475# VDD 1.18fF
C22 a_174_531# VDD 2.61fF
C23 a_340_202# VDD 0.02fF
C24 a_340_202# a_258_74# 0.13fF
C25 a_340_202# Up 0.02fF
C26 a_462_191# VDD 0.13fF
C27 a_134_73# Out 0.05fF
C28 a_174_531# a_31_494# 0.12fF
C29 a_462_143# VDD 0.23fF
C30 a_462_191# a_258_74# 0.00fF
C31 a_462_191# Up 0.09fF
C32 a_258_74# a_462_143# 0.02fF
C33 a_462_143# Up 0.08fF
C34 a_127_486# ENb 0.01fF
C35 a_248_427# Down 0.00fF
C36 a_134_73# a_248_475# 0.02fF
C37 a_248_427# VDD 0.14fF
C38 a_134_73# a_174_531# 0.01fF
C39 a_134_73# a_340_202# 0.00fF
C40 a_174_531# ENb 0.01fF
C41 a_258_74# a_248_427# 0.00fF
C42 a_248_475# Out 0.40fF
C43 a_174_531# Out 0.24fF
C44 a_127_486# a_248_475# 0.02fF
C45 a_462_191# Out 0.04fF
C46 a_127_486# a_174_531# 0.13fF
C47 Down VDD 0.05fF
C48 a_462_143# Out 0.02fF
C49 a_134_73# a_248_427# 0.09fF
C50 a_258_74# Down 0.00fF
C51 Down Up 0.15fF
C52 a_174_531# a_248_475# 2.05fF
C53 Up GND 1.42fF
C54 Out GND 2.98fF
C55 VDD GND 0.08fF
C56 a_462_143# GND 0.58fF
C57 a_462_191# GND 0.58fF
C58 a_340_202# GND 0.31fF
C59 a_258_74# GND 0.51fF
C60 a_134_73# GND 2.42fF
C61 a_248_427# GND 0.69fF
C62 a_248_475# GND 0.49fF
C63 a_127_486# GND 0.24fF
C64 a_174_531# GND 1.49fF

*r1 out rc 200
*c1 rc 0 8f

v2 ENb 0 0
v1 VDD GND 1.8
.ends cp


*VCO
.subckt vco VCtrl Clk_Out
XM1000 GND VCtrl a_19_462# GND sky130_fd_pr__nfet_01v8 w=84 l=15
+  ad=2436 pd=227.415 as=2436 ps=226
XM1001 a_653_144# a_553_144# a_109_144# GND sky130_fd_pr__nfet_01v8 w=42 l=15
+  ad=1218 pd=142 as=1218 ps=124.6
XM1002 a_453_144# a_353_144# a_109_144# GND sky130_fd_pr__nfet_01v8 w=42 l=15
+  ad=1218 pd=142 as=1218 ps=124.6
XM1003 a_553_144# a_453_144# a_109_144# GND sky130_fd_pr__nfet_01v8 w=42 l=15
+  ad=1218 pd=142 as=1218 ps=124.6
XM1004 a_353_144# a_253_144# a_109_144# GND sky130_fd_pr__nfet_01v8 w=42 l=15
+  ad=1218 pd=142 as=1218 ps=124.6
XM1005 a_253_144# a_153_144# a_109_144# GND sky130_fd_pr__nfet_01v8 w=42 l=15
+  ad=1218 pd=142 as=1218 ps=124.6
XM1006 a_153_144# a_109_205# a_109_144# GND sky130_fd_pr__nfet_01v8 w=42 l=15
+  ad=1218 pd=142 as=1218 ps=124.6
XM1007 Clk_Out a_109_205# a_393_418# VDD sky130_fd_pr__pfet_01v8 w=108 l=15
+  ad=3132 pd=274 as=3185.05 ps=291.789
XM1008 a_109_205# a_653_144# a_109_253# VDD sky130_fd_pr__pfet_01v8 w=240 l=15
+  ad=7200 pd=540 as=6960 ps=665.6
XM1009 a_653_144# a_553_144# a_109_253# VDD sky130_fd_pr__pfet_01v8 w=42 l=15
+  ad=1218 pd=142 as=1218 ps=116.48
XM1010 a_109_205# a_653_144# a_109_144# GND sky130_fd_pr__nfet_01v8 w=120 l=15
+  ad=3480 pd=298 as=3480 ps=356
XM1011 a_453_144# a_353_144# a_109_253# VDD sky130_fd_pr__pfet_01v8 w=42 l=15
+  ad=1218 pd=142 as=1218 ps=116.48
XM1012 a_553_144# a_453_144# a_109_253# VDD sky130_fd_pr__pfet_01v8 w=42 l=15
+  ad=1218 pd=142 as=1218 ps=116.48
XM1013 a_353_144# a_253_144# a_109_253# VDD sky130_fd_pr__pfet_01v8 w=42 l=15
+  ad=1218 pd=142 as=1218 ps=116.48
XM1014 a_393_418# ENb VDD VDD sky130_fd_pr__pfet_01v8 w=42 l=15
+  ad=1238.63 pd=113.474 as=1386 ps=150
XM1015 GND VCtrl a_109_144# GND sky130_fd_pr__nfet_01v8 w=108 l=15
+  ad=3132 pd=292.39 as=3132 ps=320.4
XM1016 a_253_144# a_153_144# a_109_253# VDD sky130_fd_pr__pfet_01v8 w=42 l=15
+  ad=1218 pd=142 as=1218 ps=116.48
XM1017 a_153_144# a_109_205# a_109_253# VDD sky130_fd_pr__pfet_01v8 w=42 l=15
+  ad=1218 pd=142 as=1218 ps=116.48
XM1018 Clk_Out a_109_205# GND GND sky130_fd_pr__nfet_01v8 w=54 l=15
+  ad=1566 pd=166 as=1566 ps=146.195
XM1019 a_393_418# a_19_462# a_19_462# VDD sky130_fd_pr__pfet_01v8 w=84 l=15
+  ad=2477.26 pd=226.947 as=2436 ps=226
XM1020 a_393_418# a_19_462# a_109_253# VDD sky130_fd_pr__pfet_01v8 w=108 l=15
+  ad=3185.05 pd=291.789 as=3132 ps=299.52
C0 a_353_144# a_453_144# 0.12fF
C1 a_353_144# a_253_144# 0.12fF
C2 a_19_462# a_453_144# 0.01fF
C3 a_653_144# Clk_Out 0.03fF
C4 a_109_205# a_393_418# 0.23fF
C5 a_19_462# VCtrl 0.04fF
C6 a_19_462# ENb 0.01fF
C7 VDD a_453_144# 0.02fF
C8 VDD a_253_144# 0.02fF
C9 a_653_144# a_393_418# 0.01fF
C10 a_109_205# a_553_144# 0.19fF
C11 VDD VCtrl 0.01fF
C12 VDD ENb 0.14fF
C13 a_109_205# a_109_144# 0.22fF
C14 a_353_144# VDD 0.02fF
C15 a_19_462# VDD 0.43fF
C16 a_653_144# a_553_144# 0.11fF
C17 a_653_144# a_109_144# 0.17fF
C18 a_109_205# a_109_253# 0.31fF
C19 a_393_418# a_453_144# 0.02fF
C20 a_653_144# a_109_253# 0.17fF
C21 a_393_418# ENb 0.36fF
C22 a_553_144# a_453_144# 0.12fF
C23 Clk_Out VDD 0.01fF
C24 a_393_418# a_353_144# 0.01fF
C25 a_109_205# a_153_144# 0.21fF
C26 a_109_144# a_453_144# 0.18fF
C27 a_393_418# a_19_462# 0.28fF
C28 a_109_144# a_253_144# 0.18fF
C29 ENb a_553_144# 0.00fF
C30 VCtrl a_109_144# 0.11fF
C31 a_393_418# VDD 0.49fF
C32 a_353_144# a_553_144# 0.04fF
C33 a_109_253# a_453_144# 0.19fF
C34 a_353_144# a_109_144# 0.18fF
C35 a_19_462# a_553_144# 0.00fF
C36 a_109_253# a_253_144# 0.18fF
C37 a_19_462# a_109_144# 0.01fF
C38 ENb a_109_253# 0.10fF
C39 VDD a_553_144# 0.02fF
C40 VDD a_109_144# 0.38fF
C41 a_353_144# a_109_253# 0.19fF
C42 a_19_462# a_109_253# 0.05fF
C43 a_393_418# Clk_Out 0.13fF
C44 VDD a_109_253# 0.13fF
C45 a_153_144# a_253_144# 0.12fF
C46 a_153_144# VCtrl 0.00fF
C47 Clk_Out a_109_144# 0.01fF
C48 a_153_144# a_353_144# 0.04fF
C49 a_393_418# a_553_144# 0.01fF
C50 Clk_Out a_109_253# 0.03fF
C51 a_109_205# a_653_144# 0.26fF
C52 a_153_144# VDD 0.02fF
C53 a_393_418# a_109_253# 0.33fF
C54 a_109_144# a_553_144# 0.18fF
C55 a_109_253# a_553_144# 0.18fF
C56 a_109_144# a_109_253# 0.33fF
C57 a_109_205# a_453_144# 0.15fF
C58 a_109_205# a_253_144# 0.17fF
C59 a_109_205# VCtrl 0.00fF
C60 a_109_205# ENb 0.07fF
C61 a_653_144# a_453_144# 0.04fF
C62 a_109_205# a_353_144# 0.15fF
C63 a_109_205# a_19_462# 0.00fF
C64 a_653_144# ENb 0.03fF
C65 a_153_144# a_109_144# 0.24fF
C66 a_109_205# VDD 0.25fF
C67 a_153_144# a_109_253# 0.17fF
C68 a_653_144# VDD 0.02fF
C69 a_453_144# a_253_144# 0.04fF
C70 a_109_205# Clk_Out 0.13fF
C71 VDD GND 0.09fF
C72 VCtrl GND 0.28fF
C73 a_553_144# GND 0.31fF
C74 a_453_144# GND 0.31fF
C75 a_353_144# GND 0.31fF
C76 a_253_144# GND 0.33fF
C77 a_153_144# GND 0.32fF
C78 a_109_205# GND 1.62fF
C79 a_109_253# GND 1.89fF
C80 a_109_144# GND 1.78fF
C81 a_653_144# GND 0.33fF
C82 a_393_418# GND 0.66fF
C83 a_19_462# GND 1.44fF

*c1 11 0 24f
v2 ENb 0 0
v1 VDD GND 1.8
.ends vco


*FD
.subckt fd Clk_In Clk_Out

XM1000 a_79_75# Clk_In VDD VDD sky130_fd_pr__pfet_01v8 w=72 l=15
+  ad=2088 pd=202 as=1824 ps=170.667
XM1001 GND a_597_66# a_787_62# GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=912 pd=110.667 as=1116 ps=134
XM1002 a_332_67# a_79_75# a_190_75# VDD sky130_fd_pr__pfet_01v8 w=42 l=15
+  ad=1218 pd=142 as=1218 ps=126.737
XM1003 a_463_74# a_332_67# VDD VDD sky130_fd_pr__pfet_01v8 w=72 l=15
+  ad=2088 pd=217.263 as=1824 ps=170.667
XM1004 a_79_75# Clk_In GND GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=1044 pd=130 as=912 ps=110.667
XM1005 a_190_75# a_143_127# GND GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=1044 pd=106.8 as=912 ps=110.667
XM1006 a_143_127# a_597_66# VDD VDD sky130_fd_pr__pfet_01v8 w=72 l=15
+  ad=2088 pd=202 as=1824 ps=170.667
XM1007 a_597_66# a_79_75# a_463_74# GND sky130_fd_pr__nfet_01v8 w=84 l=15
+  ad=2436 pd=226 as=2436 ps=249.2
XM1008 a_143_127# a_597_66# GND GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=1044 pd=130 as=912 ps=110.667
XM1009 VDD a_597_66# a_787_62# VDD sky130_fd_pr__pfet_01v8 w=72 l=15
+  ad=1824 pd=170.667 as=2232 ps=206
XM1010 Clk_Out a_787_62# GND GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=1044 pd=130 as=912 ps=110.667
XM1011 a_190_75# a_143_127# VDD VDD sky130_fd_pr__pfet_01v8 w=72 l=15
+  ad=2088 pd=217.263 as=1824 ps=170.667
XM1012 a_332_67# Clk_In a_190_75# GND sky130_fd_pr__nfet_01v8 w=84 l=15
+  ad=2436 pd=226 as=2436 ps=249.2
XM1013 a_597_66# Clk_In a_463_74# VDD sky130_fd_pr__pfet_01v8 w=42 l=15
+  ad=1218 pd=142 as=1218 ps=126.737
XM1014 Clk_Out a_787_62# VDD VDD sky130_fd_pr__pfet_01v8 w=72 l=15
+  ad=2143 pd=204 as=1824 ps=170.667
XM1015 a_463_74# a_332_67# GND GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=1044 pd=106.8 as=912 ps=110.667
C0 VDD a_143_127# 0.38fF
C1 VDD Clk_Out 0.10fF
C2 a_332_67# a_463_74# 0.12fF
C3 a_332_67# a_190_75# 0.28fF
C4 Clk_Out a_143_127# 0.04fF
C5 VDD a_79_75# 0.37fF
C6 Clk_In a_597_66# 0.17fF
C7 a_79_75# a_143_127# 0.84fF
C8 VDD a_463_74# 0.19fF
C9 VDD a_190_75# 0.22fF
C10 a_463_74# a_143_127# 0.21fF
C11 a_190_75# a_143_127# 0.20fF
C12 VDD a_787_62# 0.21fF
C13 a_463_74# a_79_75# 0.12fF
C14 a_787_62# a_143_127# 0.12fF
C15 a_190_75# a_79_75# 0.29fF
C16 Clk_Out a_787_62# 0.17fF
C17 Clk_In a_332_67# 0.14fF
C18 a_463_74# a_190_75# 0.04fF
C19 a_332_67# a_597_66# 0.02fF
C20 VDD Clk_In 1.10fF
C21 VDD a_597_66# 0.19fF
C22 Clk_In a_143_127# 1.17fF
C23 a_597_66# a_143_127# 0.64fF
C24 Clk_Out a_597_66# 0.01fF
C25 Clk_In a_79_75# 0.60fF
C26 a_597_66# a_79_75# 0.03fF
C27 Clk_In a_463_74# 0.20fF
C28 Clk_In a_190_75# 0.30fF
C29 a_463_74# a_597_66# 0.32fF
C30 VDD a_332_67# 0.15fF
C31 Clk_In a_787_62# 0.01fF
C32 a_332_67# a_143_127# 0.19fF
C33 a_787_62# a_597_66# 0.44fF
C34 a_332_67# a_79_75# 0.16fF
C35 VDD GND 3.76fF
C36 a_787_62# GND 0.47fF
C37 a_597_66# GND 1.33fF
C38 a_463_74# GND 0.36fF
C39 a_332_67# GND 0.44fF
C40 a_190_75# GND 0.38fF
C41 a_79_75# GND 1.06fF
C42 a_143_127# GND 0.99fF 


*c1 7 0 18f
v1 VDD GND 1.8
.ends fd
```

- To simulate the code type first, enter the directory where the file is saved using the "cd" command in terminal.
- Now simulate the file using the ngspice command as shown below:

![pll_post_layout_terminal](https://user-images.githubusercontent.com/89193562/133931599-a9f8f96c-179e-481c-9475-708b0775d5da.JPG)

- We are going to receive two plot outputs for this file because of the following lines in the ".control" instruction:

```
.control
tran 0.1ns 180us
plot v(Clk_Ref) v(Clk_Out_by_8) v(Clk_Out_by_4)+2 v(Clk_Out_by_2)+4 v(Clk_Out)+6 v(up)+8 v(down)+10 v(VCtrl)+12
plot v(Clk_Ref) v(Clk_Out_by_8)+2
.endc
```

- The first post-layout plot that we receive is much like the pre-layout plot:

![pll_post_layout_tran1](https://user-images.githubusercontent.com/89193562/133931663-368f7af0-45f9-4b04-b6d5-04d7f0a25859.JPG)

- When we zoom into into it we get:

![pll_post_layout_tran1_zoom](https://user-images.githubusercontent.com/89193562/133931677-9d86219f-c777-4548-8c3e-b787fa307e09.JPG)

- We zoom in further into the plot to get:

![pll_post_layout_tran1_zoomed_even more](https://user-images.githubusercontent.com/89193562/133931732-7ef89c03-c5ea-42cc-8b7f-e8131b176ec9.JPG)

- Finally when we zoom in onto the region 99.9us and 100us we get:

![pll_post_layout_tran1_zoomed_even_further_beyond](https://user-images.githubusercontent.com/89193562/133931756-393a909d-6498-4843-8afb-dc8173a03ed2.JPG)

- The second plot that we get is the output clock and reference clock signals plotted as:

![pll_post_layout_tran2](https://user-images.githubusercontent.com/89193562/133931789-69d49b36-21e2-49bb-a0e2-3528e9541e87.JPG)

- When we zoom into it we get:

![pll_post_layout_tran2_zoom](https://user-images.githubusercontent.com/89193562/133931801-36bbed64-b12e-436e-b014-a2627e659540.JPG)

- We zoom in further into the plot to get:

![pll_post_layout_tran2_zoom_even more](https://user-images.githubusercontent.com/89193562/133931811-1ebd238f-4dcf-4817-a608-d11d89f8afc9.JPG)

### For the mcq on post layout simulation

- Create a new directory containing "sky130nm.lib" and "PFD.spice" in it.
- Enter this directory through the terminal and type the command `nano PFD_postlay.cir`
- Type the following code in it:

```
.include sky130nm.lib
.include PFD.spice

xx1 Ref_Clk Up Down Clk2 GND VCC PFD

v1 VDD GND 1.8v

v2 Ref_Clk GND PULSE 0 1.8v 0 6p 6p 40n 80n

v3 Clk2 GND PULSE 0 1.8v 0.25n 6p 6p 40n 80n

.control 
tran 0.1n 5u
plot v(Up) v(Down)+2 v(Ref_Clk)+4 v(Clk2)+6
.endc

.end
```

- In the terminal, it looks like:

![pfd_postlay_mcq_file](https://user-images.githubusercontent.com/89193562/133926198-814e689e-c273-49e6-88ce-72e30de6dcfb.JPG)

- The output that we receive looks like:

![pfd_postlay_mcq_tran](https://user-images.githubusercontent.com/89193562/133926212-614acb31-7cb5-4bc4-96b0-1a1864ceaf05.JPG)

- And the zoomed output looks like:

![pfd_postlay_mcq_tran_zoom](https://user-images.githubusercontent.com/89193562/133926223-d65c2806-1bdd-4f7d-9fa5-3b093dfa31b8.JPG)

- In this case the up signal is just a pulse because of the "Dead zone".

## Part 17: Steps to combine layouts

- Open magic using the command `magic -T sky130A.tech` in the terminal.
- From the cells option choose place instance. The place instace option allows us to place more than one pre-created circuits in the magic window.
- Press the "I" button and then the "X" button on the keyboard to open the circuit or to make the circuit visible.
- Now open all layouts in the same window.
- Make quick connections using the wire tool. To access the wire tool press the space bar once and to exit the wire tool press the space bar three more times.
- Once this is done the magic interface looks as follows:

![magic_wire_connection](https://user-images.githubusercontent.com/89193562/133928204-1415170b-997d-45f7-b6fc-82da6d74b48e.JPG)

- Extend the layers to make connections between the subcircuits.

In the final PLL design:
- On the right hand side, there is a multiplexer. It is kept to select between the charge pump or an external source to control the VCO.
- On the top left, there are three frequency dividers. The output from them is the feed-back loop and it goes to the PFD on the bottom left.
- The PFD also has the reference clock as input. PFD converts the inputs into the Up or Down signals that control the charge pump at the bottom right.
- The output voltage generated by the charge pump in turn controls the VCO and generates the output that we want.
- After Charge Pump, we must place the loop filter.

Two things that we need to do once we reach till here:
- Extract spice netlist and perform the final post layout simulation.
- Save that file as a "GDS" file.
    - The GDS file is the complete layout information that we can send to the fabricatoin centre to fabricate the IC.
    - To write GDS file, go to the file menu and choose the "Write GDS" option.
    - This gives us our final IC design in ".gds" format.

- The final PLL layout looks as follows:

![pll_final_design](https://user-images.githubusercontent.com/89193562/133928332-e8cb24a8-5604-447f-86ed-ced573cfb019.JPG)

## Part 18: Tapeout theory

- Tapeout means to send our final design to the Fab, after preparing it.
- Preparing the requires adding the following to the chip:
    - Input-Output Pads
    - Peripherals
    - Memory
    - Testing Mechanisms
    - Others

**Caravel:**
- The input-output pads, processor, memory, peripherals and the other most important things that one wants to support his design with are available on the SoC.

![2021-09-19 (2)](https://user-images.githubusercontent.com/89193562/133928499-3599f22b-6959-4a4c-9dd9-c055a9dd4e88.png)

- The user project area we see is the area available to us to place our design.
- In a way the this SoC acts as a vehicle that carries our design and hence the name 'Caravel'.
- This is the IC that finally gets fabricated with our design inside it.
- During the first shuttle the process was to place and design inside the user project area and then meet the connections form the design ports to the user project area pins and then merge that user project area into the Caravel SoC.
- This time around they say that the designer only needs to bother about placing their design in the user project area and need not have to bother about integrating it to the SoC.

## Part 19: Tapeout labs

- Download the layout file for the analog user project area.
- Once downloaded, extract it to the directory of your choice.
- Now, open it with magic and the technology file sky130A.tech
- Place the design in the user project area and make the connections with the pins.
- It is important to not that one must not move any of the pins that they have given from their location. We only use the pins that we need and connect our design to them.
- At the bottom of the user project area are the wishful ports.
- Along the left of the user project area are the input-output ports and some power ports like Vdd and Vss.
- Along the right of the user project area are a few more input-output ports and power ports like Vccd, Vssd, Vcca and Vssa.
- At the top of the user project area are the analog input-output pins.

- In our design, we have five pins:
    - Enable pins for CP and VCO.
    - Reference clock input pin.
    - Output clock pin.
    - VCO direct input pin.
- The enable pins are connected to the digital input-output pins.
- Reference clock input pin and output clock pin are also digital and so we connect them to the digital input-output pins.
- VCO direct input pin is control voltage pin of analog nature. So, we need to connect it to an analog input-output pin.
- Considering this scenarion, we place our design at the top-right corner and make the connections to the pins using wire tool and contact layers.


- \*\***_This is the end of the tasks of the second day._**

# Conclusion and Opinion

The workshop was very helpful to me because I was able to explore the concepts of PLL to a great depth. My learning throughout the workshop was non-stop. I grasped the basics of PLL quite thoroughly which helped a lot in understanding the later part of the workshop. I was able to get hands on using experience with the open-source EDA tools which was really beneficial (the tools being magic and ngspice). The design flow was maintained throughout the workshop which helped me to get familiar with it. The simulations and layouts were tricky at the start but got easier as I explored the tools. Finally, this workshop cleared all my basic concepts of the PLL and the experience of getting a Silicon Proven Model ready was amazing.

# References
- [https://github.com/lakshmi-sathi/avsdpll_1v8](https://github.com/lakshmi-sathi/avsdpll_1v8)
- [https://drive.google.com/file/d/18BG4zzpRrcHP0UoBcNLA3sWFDVdNlUtp/view](https://drive.google.com/file/d/18BG4zzpRrcHP0UoBcNLA3sWFDVdNlUtp/view)
- [https://github.com/google/skywater-pdk-libs-sky130_fd_pr.git](https://github.com/google/skywater-pdk-libs-sky130_fd_pr.git)
