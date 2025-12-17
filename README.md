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

```
UP COUNTER
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

DOWN COUNTER
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


Developed by: nanditha shaji

RegisterNumber:25012970
*/

**RTL LOGIC UP COUNTER**
counter up
<img width="751" height="404" alt="image" src="https://github.com/user-attachments/assets/e2b960cf-8d7c-48af-8eb1-84bcbb5178ff" />

counter down
<img width="771" height="376" alt="image" src="https://github.com/user-attachments/assets/3ceabeb7-6a6b-497d-bf54-434e5565c7eb" />


**TIMING DIAGRAM FOR IP COUNTER**
up counter
<img width="771" height="377" alt="image" src="https://github.com/user-attachments/assets/7b24ebeb-9912-45a0-b768-e531efb379a7" />

down counter

<img width="764" height="393" alt="image" src="https://github.com/user-attachments/assets/b9ba94f0-ef69-4beb-92cc-2662f0ebd5ba" />


**TRUTH TABLE**

<img width="364" height="376" alt="image" src="https://github.com/user-attachments/assets/4efb4f7c-c89a-470d-9b0b-8343959e6da4" />


**RESULTS**

Thus implemented 4 bit synchronous up counter and validate functionality.
