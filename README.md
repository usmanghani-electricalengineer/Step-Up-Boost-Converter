# Step Up Boost Converter ( DC to DC )
This project involves the design and implementation of a Boost Converter, a DC-to-DC step-up circuit that increases the input voltage level. The system efficiently converts a 12V DC input into an 18V DC output, demonstrating the principle of voltage boosting using inductor energy storage and controlled switching.

## Power Supply Preparation
If a DC source is not available, we first convert AC to DC before feeding it to the boost converter.
1. **AC Input:** Single-phase AC (220V) supply  
2. **Step-Down Transformer:** Reduces 220V AC → 12V AC  
3. **Bridge Rectifier:** Converts 12V AC → Pulsating DC  
4. **Capacitor Filter:** Smooths the pulsating DC into a steady DC  
5. **Boost Converter Input:** Smooth DC (12V) fed to converter  
6. **Boost Converter Output:** Higher DC (18V) obtained  

## Working Principle of Boost Converter
The working of a boost converter can be divided into **two operating modes**:
### Mode 1 – Switch ON (Energy Storage Phase)
- The **MOSFET (M1)** is turned **ON** by a **HIGH** signal from the 555 Timer IC.  
- The **input current (VIN)** flows through the **inductor (L1)** and the **MOSFET**, storing energy in the inductor’s magnetic field.  
- The **diode (D1)** is **reverse-biased**, so no current flows to the output.  
- The **load** continues to receive power from the **capacitor (C1)**.
**Key Points**
- Inductor **stores energy**.  
- Diode **OFF (reverse-biased)**.  
- MOSFET **ON**.  
- Current path: `VIN → L1 → M1 → GND`.  
### Mode 2 – Switch OFF (Energy Release Phase)
- The **MOSFET** turns **OFF** when the 555 Timer sends a **LOW** signal.  
- The **inductor (L1)** releases its stored energy to maintain current flow.  
- The **induced voltage (VL)** adds to the **input voltage (VIN)**.  
- The **diode (D1)** becomes **forward-biased**, allowing current to charge the **capacitor (C1)** and supply the **load**.
**Key Points**
- Inductor **releases stored energy**.  
- Diode **ON (forward-biased)**.  
- MOSFET **OFF**.  
- Current path: `L1 → D1 → C1 → Load → GND`.

## Role of 555 Timer IC
The **555 Timer IC** operates in **Astable Mode** to generate a continuous **square wave** that controls the **MOSFET switching**.
- **HIGH Pulse:** MOSFET turns **ON** → Mode 1 (Energy Storage)  
- **LOW Pulse:** MOSFET turns **OFF** → Mode 2 (Energy Release)
The **frequency** and **duty cycle** of this waveform depend on the values of **resistors (R1, R2)** and **capacitors (C1, C2)** in the timer circuit.

## Components Used
| Component | Description |
|------------|-------------|
| **12V DC Input / Transformer Source** | Power input to the circuit |
| **Step-Down Transformer** | Converts 220V AC → 12V AC |
| **Bridge Rectifier** | Converts AC → DC |
| **Filter Capacitor** | Smooths pulsating DC |
| **Inductor (L1)** | Stores energy during ON cycle |
| **Diode (D1)** | Ensures one-way current flow |
| **MOSFET (M1)** | Acts as a switching device |
| **555 Timer IC** | Generates control pulses |
| **Output Capacitor (C1)** | Stores charge and maintains output voltage |
| **Load** | Receives boosted voltage output |

## Output Characteristics
- **Input Voltage:** 12V DC  
- **Output Voltage:** 18V DC (approx.)  
- **Operation:** Continuous switching between Mode 1 and Mode 2  
- **Efficiency:** Depends on component quality and switching frequency
  
## Conclusion
The **Boost Converter** efficiently converts a **lower DC voltage** into a **higher DC voltage** using energy storage and release in an inductor, controlled by the **MOSFET** and **555 Timer IC**.  


