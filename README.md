# DAC
 INTERFACING DAC WITH 8086 KIT AND GENERATING SAWTOOTH AND SQUARE WAVEFORMS

## AIM
To write an assembly language program in 8086 to generate Sawtooth and Square waveforms using DAC.

---

## APPARATUS REQUIRED

| S. No | Item              | Specification   | Quantity |
|-------|------------------|-----------------|----------|
| 1     | Microprocessor kit | 8086            | 1        |
| 2     | Power Supply      | +5 V DC, +12 V DC | 1      |
| 3     | DAC Interface board | -              | 1        |

---

## ALGORITHM

### Measurement of Analog Voltage
1. Send the digital value to DAC.  
2. Read the corresponding analog value at its output.  

### Waveform Generation

#### Square Waveform
1. Send low value (00) to the DAC.  
2. Introduce suitable delay.  
3. Send high value to DAC.  
4. Introduce delay.  
5. Repeat the above procedure.  

#### Sawtooth Waveform
1. Load low value (00) to accumulator.  
2. Send this value to DAC.  
3. Increment the accumulator.  
4. Repeat step (ii) and (iii) until accumulator value reaches FF.  
5. Repeat the above procedure from step 1.  

---

## PROGRAMS

# 8086 Assembly Programs – DAC Interfacing

## Program: Square Wave

| Memory Location | Program     | Comments                          |
|-----------------|-------------|-----------------------------------|
| 1000            | MOV AL,00H  | Load 00H in Accumulator           |
| 1003            |  OUT 0C8H,AL | Send through output port         |
| 1005            |  CALL DELAY(1100)  | CALL PROGRAM TO 1100      |
| 1008            |  MOV AL,0FFH |   Load 00H in Accumulator       |
| 100A            |   OUT 0C8H,AL|  Send through output port       |
| 100D            |  CALL DELAY(1100) | CALL PROGRAM TO 1100       |


| Memory Location | Program     | Comments                          |
|-----------------|-------------|-----------------------------------|
| 1100            | MOV CX,0505  | Load 0505H in Accumulator           |
| 1103            |  DEC CX | Decrement CX        |
| 1105           |  JNZ 1104  | RPEAT UNTILL ZERO      |
| 1108            |   RET |   RETURN TO MAIN PROGRAM      |


# Program: Sawtooth wave

## Assembly Program

| Memory Location | Program Instruction   | Comments                        |
|-----------------|-----------------------|---------------------------------|
| `1000`          | `START: MOV AL,00H`  | Load `00H` in accumulator       |
| `1003`          | `LOOP : OUT 0C8H,AL` | Send through output port        |
| `1005`          | `INC AL`             | Increment contents of accumulator |
| `1007`          | `JNC LOOP`           | Jump if no carry (continue loop) |
| `1009`          | `JMP START`          | Go to starting location         |

---

## Tabulation

| Waveform  | Amplitude | Time period | 
|-----------|-----------|-------------|
| Sawtooth  |           |             | 
| Square    |           |             |
---

## Model Graph

*(Insert graph/diagram here if available)*
<img width="916" height="775" alt="image" src="https://github.com/user-attachments/assets/556f63c7-4f67-4fe6-bfa8-94d52fca66ab" />
<img width="851" height="723" alt="image" src="https://github.com/user-attachments/assets/a9526af0-d118-4936-8904-f83a0d79f4f2" />





## OUTPUT IMAGE OF DAC(SAWTOOTH WAVE FROM DSO AND SQUARE WAVE FROM DSO)
<img width="1280" height="576" alt="image" src="https://github.com/user-attachments/assets/d529830e-86a0-4ca4-bf49-e202ef32a79a" />
<img width="1280" height="576" alt="image" src="https://github.com/user-attachments/assets/95844754-3040-43d8-bf8b-f0d44054c789" />
<img width="1280" height="576" alt="image" src="https://github.com/user-attachments/assets/db7b6b65-4810-418e-8021-298c7b4a316e" />
<img width="1280" height="576" alt="image" src="https://github.com/user-attachments/assets/12b8b5db-ddc9-47af-b034-242380c65229" />







## Result

Thus, the **DAC was interfaced with 8086** and different **waveforms** were successfully generated.




