# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](![UP COUNTER PIC](https://github.com/premsuryas/Exp-7-Synchornous-counters-/assets/147473858/098a015e-17c0-4857-b592-48f3a3ddf884)
.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](![DOWN COUNTER PIC](https://github.com/premsuryas/Exp-7-Synchornous-counters-/assets/147473858/3012297a-992f-4ad7-9a44-60ddcca95afa)
.png)


4-bit Count Down Counter
### Procedure
/* write all the steps invloved */



### PROGRAM 
/*UP COUNTER
module upc (clk,A);
input clk;
output reg [0:3]A;
always@ (posedge clk)
begin
A[0]=((A[1])&(A[2])&(A[3]))^A[0];
A[1]=((A[2])&(A[3]))^A[1];
A[2]=((A[3]))^A[2];
A[3]=1^A[3];
end
endmodule
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by:PREM KUMAR .S 
RegisterNumber:23013598  
*/ DOWN COUNTER
module downcounter (clk,A);
input clk;
output reg [0:3]A;
always@ (posedge clk)
begin
A[0]=((~A[1])&(~A[2])&(~A[3]))^A[0];
A[1]=((~A[2])&(~A[3]))^A[1];
A[2]=((~A[3]))^A[2];
A[3]=1^A[3];
end
endmodule






### RTL LOGIC UP COUNTER AND DOWN COUNTER  
![image](![UP RTL](https://github.com/premsuryas/Exp-7-Synchornous-counters-/assets/147473858/c4abc9c8-84e3-4f27-8c87-f64efe997570)
)

### DOWN RTL
![image](![down counter RTL](https://github.com/premsuryas/Exp-7-Synchornous-counters-/assets/147473858/a2957310-37bd-44c2-b872-eb0ee8b5e209)
)






### TIMING DIGRAMS FOR COUNTER  
### TIMING UP COUNTER
![image](![UP COUNTER TIMING DIAGRAM](https://github.com/premsuryas/Exp-7-Synchornous-counters-/assets/147473858/5138dc01-ee46-4a19-85b1-31f448b0cd52)
)
### down timing diagram
![image](![DWN COUNTER TIMING DIAGRAM](https://github.com/premsuryas/Exp-7-Synchornous-counters-/assets/147473858/b3f3fb57-254f-4fad-bb3e-cd250c5c11fc)
)





### TRUTH TABLE 
### UP COUNTER TRUTH TABLE
![image](![TRUTH TABLE UPC](https://github.com/premsuryas/Exp-7-Synchornous-counters-/assets/147473858/92f2e83c-b58b-48a1-aba7-e95eb69de0d5)
)
### DOWN COUNTER TRUTH TABLE 
![image](![TRUTH TABLE FOR DWC](https://github.com/premsuryas/Exp-7-Synchornous-counters-/assets/147473858/ac390655-385a-4f9b-a56f-3960b947851b)
)






### RESULTS 
when the up counter and down counter was created sucessfully
