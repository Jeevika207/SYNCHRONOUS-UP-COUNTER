### SYNCHRONOUS-UP-COUNTER

EXP-11

DATE-10-12-2024

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

1.Type the Verilog program in Quartus Prime to implement the 4 bit synchronous upcounter and validate functionality.

2.Compile and run the program to ensure the design is error-free.

3.Generate the RTL schematic to visualize the cascading D flip-flop connections and save it for documentation.

4.Create nodes for the serial input (SI), clock (CLK), and serial output (SO) to observe the shifting process during simulation.

5.Simulate the design for different input serial data patterns and observe the timing diagrams.


**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. */

module syn_counter(out,clk,rst);

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


Developed by:JEEVIKA.R

RegisterNumber: 24900508

**RTL LOGIC UP COUNTER**

![image](https://github.com/user-attachments/assets/c29d8186-f5fa-4c61-a8d1-8b892c7bf3f7)

**TIMING DIAGRAM FOR IP COUNTER**

![image](https://github.com/user-attachments/assets/d6070b68-d4f2-49bc-a79a-03ee84e8f087)

**TRUTH TABLE**

![image](https://github.com/user-attachments/assets/ef931058-c7e4-4920-aab3-62689ea5d01a)

**RESULTS**

Thus, the 4 bit synchronous up counter and validate functionality is implemented using Verilog, and its functionality is validated with the truth table and timing diagrams
