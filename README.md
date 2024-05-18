# EXPERIMENT-5 SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE
# DATE:
# AIM:
 To simulate and synthesis finite state machine using vivado.
# APPARATUS REQUIRED: 
  vivado 2023.2.
# PROCEDURE: 
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

# Logic Diagram :
![image](https://github.com/Irakamchaitanya/VLSI-LAB-EXP-5/assets/161814091/054addd3-c5f0-4908-bb0b-bb40763ed825)
# VERILOG CODE:
module fsm(clk, rst, x, z);

input clk, rst, x;

output z;

reg [2:1] present_state, NEXT_STATE;

parameter S0=2'b00, S1=2'b01, S2=2'b10, S3=2'b11;

always@(x,present_state)

case(present_state)

S0: if(x)

NEXT_STATE=S1;

else

NEXT_STATE=S0;

S1: if(x)

NEXT_STATE=S1;

else

NEXT_STATE=S2;

S2: if(x)

NEXT_STATE=S3;

else

NEXT_STATE=S0;

S3: if(x)

NEXT_STATE=S1;

else

NEXT_STATE=S2;

endcase

always@(negedge rst, posedge clk)

if(rst)

present_state<=S0;

else

present_state<=NEXT_STATE;

assign z=(present_state==S3);

endmodule

# OUTPUT:
![image](https://github.com/Irakamchaitanya/VLSI-LAB-EXP-5/assets/161814091/de3b7907-59e5-480c-9fe5-cbf9f712b4de)
# RESULT:
Thus,the simulation and synthesis of finite state machine by using vivado has been successfully excecuted and verified.
