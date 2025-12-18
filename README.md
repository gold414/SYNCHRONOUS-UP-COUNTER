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

**PROGRAM**

UP COUNTER
```
module UD_counter(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
	if(!rst)
		out<=0;
	else 
		out <= out+1;
end
endmodule
```

DOWN COUNTER
```
module UD_counter(out,clk,rst);
input clk,rst; 
output reg [3:0]out;
always @ (posedge clk)
begin
if(!rst)
	out<=4'b1111;
else 
	out <= out-1;
end
endmodule

```
Developed by: THANGAPAZHAM P
RegisterNumber: 25017581

**RTL LOGIC UP COUNTER**

<img width="913" height="370" alt="Screenshot 2025-12-18 075740" src="https://github.com/user-attachments/assets/0a61aec0-498e-456b-b875-b5bfe1fadbb4" />


**TIMING DIAGRAM FOR IP COUNTER**

<img width="1920" height="1080" alt="Screenshot (165)" src="https://github.com/user-attachments/assets/46294b9e-593c-41cd-aad4-bc9ee2118892" />


**TRUTH TABLE**

![WhatsApp Image 2025-12-17 at 8 25 06 PM](https://github.com/user-attachments/assets/54ad4a5f-97d3-4c1a-b437-dbc43ac5de3f)


**RESULTS**

Thus the Synchronous 3 bit Up counter is implemeted and verified.
