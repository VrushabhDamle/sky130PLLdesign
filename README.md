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
        - [For the mcq on post layout simulation](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#for-the-mcq-on-post-layout-simulation)
    - [Part 17: Steps to combine layouts](https://github.com/VrushabhDamle/sky130PLLdesignWorkshop/blob/main/README.md#part-17-steps-to-combine-layouts)
    - [Part 18: Tapeout theory]()
    - [Part 19: Tapeout labs]()
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

**Photos taken from the workshop slides**

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

## Part 18: Tapeout theory



# References
- [https://github.com/lakshmi-sathi/avsdpll_1v8](https://github.com/lakshmi-sathi/avsdpll_1v8)
