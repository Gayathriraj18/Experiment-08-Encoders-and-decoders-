# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure :

Step 1: Open Quartus II and select new project and choose the file location.

Step 2: Module Declaration. Module should have the file name.

Step 3: Input-Output Delecaration.

Step 4: Use assign to define the functionality of logic circuits.

Step 5: At the end give endmodule.

Step 6: Run the program and choose RTL viewer to get RTL realization.


### PROGRAM :
```
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: Gayathri A
RegisterNumber:  212221230028
*/
# ENCODER:
module ex008(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule

# DECODER :
module ex8(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0=(~a&~b&~c); 
assign d1=(~a&~b&c);
assign d2=(~a&b&~c);
assign d3=(~a&b&c);
assign d4=(a&~b&~c);
assign d5=(a&~b&c);
assign d6=(a&b&~c);
assign d7=(a&b&c);
endmodule
```


### RTL LOGIC :

![ge1](https://user-images.githubusercontent.com/94154854/199724331-6dbfd48b-22f6-48fc-9634-8d48034cc7d1.png)


![gd1](https://user-images.githubusercontent.com/94154854/199724280-467eab59-30e9-42d6-86f6-810c869dc7c7.png)








### TIMING DIGRAMS  :

# ENCODER :

![GE1](https://user-images.githubusercontent.com/94154854/200151911-368f827b-ba8b-41bc-99ed-d7f65d0460a4.png)

![GE2](https://user-images.githubusercontent.com/94154854/200151914-e41ad525-2eb9-4917-bca1-58a1d4269fac.png)

![GE3](https://user-images.githubusercontent.com/94154854/200151915-a6580cad-de2d-4ca1-9fa3-b1362a91c66b.png)



# DECODER :

![gd2](https://user-images.githubusercontent.com/94154854/199724527-81c9d4ce-1708-474a-8180-71da4536556a.png)



### TRUTH TABLE :

# ENCODER :

![gt1](https://user-images.githubusercontent.com/94154854/200151836-0b8a17f7-6cb2-47eb-8674-4591be8d5dab.png)


#DECODER :

![gt2](https://user-images.githubusercontent.com/94154854/200151846-20dd1909-06cd-41a8-80e8-41ba0b024679.png)

### RESULTS :

To implement 8 to 3 Encoder and 3to8 Decoder using verilog is successfully done.
