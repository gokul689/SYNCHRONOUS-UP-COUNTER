### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

/* write all the steps invloved */
Step 1: Open Quartus II in your laptop. Step 2: Write
code to implement SR flipflop using verilog and validating their functionality using their
functional tables. Step 3: Run compilation to check for errors. Step 4: Open waveform
output and load input values. Step 5: Run simulation to get the output. Step 6: Open in
RTL viewers to get RTL diagram output.


**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by: Gokul Prasad RegisterNumber:212224050011
*/
UPCOUNTER:
```
module ex11(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
if(rst)
out<=0;
else
out <= out+1;
end
endmodule
```
DOWNCOUNTER:
```
module ex12(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
if(rst)
out<=0;
else
out <= out-1;
end
endmodule
```

**RTL LOGIC UP COUNTER**

UPCOUNTER:

![Screenshot 2025-04-29 220709](https://github.com/user-attachments/assets/df25b1b9-ad1b-46a2-8080-42db07ce7ba5)

DOWNCOUNTER:

![Screenshot 2025-04-29 223326](https://github.com/user-attachments/assets/2214d540-b53c-4ff1-a130-8e0eb33d346d)

**TIMING DIAGRAM FOR IP COUNTER**

UPCOUNTER:

![Screenshot 2025-04-29 221204](https://github.com/user-attachments/assets/cf42e520-dd96-4201-8dd9-38b068b497b6)

DOWNCOUNTER:

![Screenshot 2025-04-29 223531](https://github.com/user-attachments/assets/758f06aa-5cc4-42ad-b032-8bd574960b41)

**TRUTH TABLE**

UPCOUNTER:

![image](https://github.com/sanjayy2431/Exp-7-Synchornous-counters-/assets/149365143/9061b16e-f9e1-4fb3-988c-20a8c31b7400)

DOWNCOUNTER:

![image](https://github.com/sanjayy2431/Exp-7-Synchornous-counters-/assets/149365143/2d712296-1862-42f2-b0d0-d099a6c92c7b)


**RESULTS**

Thus the program to implement a 4 bit synchronous up counter using verilog and validating their
functionality using their functional tables is successfully completed.
