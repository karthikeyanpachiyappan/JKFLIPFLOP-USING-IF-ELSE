# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/karthikeyanpachiyappan/JKFLIPFLOP-USING-IF-ELSE/assets/155143878/d989eadc-c2f4-46ff-9f8b-dd8e0564dddc)



This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/karthikeyanpachiyappan/JKFLIPFLOP-USING-IF-ELSE/assets/155143878/5d9112fe-78c3-4088-9de2-56dc4a96deb1)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/karthikeyanpachiyappan/JKFLIPFLOP-USING-IF-ELSE/assets/155143878/c924ba45-cc55-47f9-ad75-ef395f585682)


By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/karthikeyanpachiyappan/JKFLIPFLOP-USING-IF-ELSE/assets/155143878/4269e9f5-51ab-4c66-b53b-e67089a85e1c)


The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**

1.Go to quartus software.  

2.Set new environment.

3.Type the code to implement SR flipflop using verilog and validating their functionality using their functional tables.

 4.Run the program.
 
 5.Give inputs in the waveform table.
 
 6.Run the program.
 
**PROGRAM**

```
Developed by : Karthikeyan P
Reg no: 212223230102
```
```verilog
module JK(q, qb,j,k,clock,reset);
    input j,k,clock,reset;
    output reg q, qb;
	 
always @ (posedge (clock))

    begin 
        if (!reset)
            begin
               q <= q;
               qb <=qb;
            end   
        
else
	begin
		if(j==0&&k==0)
			begin
			q<=q;
			qb<=qb;
			end
		else if(j!=k)
			begin
			q<=j;
			qb<=k;
			end
		else if(j==1&&k==1)
			begin
			q<=~q;
			qb<=~qb;
			end
	end
end
            
endmodule
```
**RTL LOGIC FOR FLIPFLOPS**

![image](https://github.com/karthikeyanpachiyappan/JKFLIPFLOP-USING-IF-ELSE/assets/155143878/d367ba15-25ee-4630-a05a-0626fafbdbdc)



**TIMING DIGRAMS FOR FLIP FLOPS**
![image](https://github.com/karthikeyanpachiyappan/JKFLIPFLOP-USING-IF-ELSE/assets/155143878/be38b0e6-1139-407a-ba1e-6cb6b9b25c27)



**RESULTS**


 Implementation of JK flipflop using verilog and validating their functionality using their functional tables is executed and the output is verified successfully
