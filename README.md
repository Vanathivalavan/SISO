# SISO
AIM:
To implement SISO Shift Register using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

#THEORY
SISO shift Register

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.
The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.


<img width="752" height="236" alt="image" src="https://github.com/user-attachments/assets/f956a626-dbbf-4f3a-99c7-4629ebe88cad" />

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next. Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.


#Procedure
Identify the serial input, clock, and serial output requirements.

Cascade a number of flip-flops (usually D flip-flops) equal to the number of bits.

Connect the output of each flip-flop to the input of the next stage.

Apply the clock so data shifts one stage forward on each clock pulse.

Verify that the data appears at the serial output after the required number of clock cycles.

#PROGRAM
```
Shift register(SISO)
----------------------------------------------------
module shift_register_3bit (
    input  wire clk,     // clock input
    input  wire rst,     // synchronous reset
    input  wire serial_in, // serial data input
    output reg  [2:0] q   // 3-bit register output
);

always @(posedge clk) begin
    if (rst)
        q <= 3'b000;          // reset all bits
    else
        q <= {q[1:0], serial_in}; // shift left
end

endmodule

```
Developed by: VANATHI T

RegisterNumber: 25013590

RTL LOGIC FOR SISO Shift Register
<img width="1920" height="1020" alt="Screenshot 2025-12-15 195651" src="https://github.com/user-attachments/assets/f0850204-4bef-4dfc-bfa4-e3f6f0bdfc2d" />

TIMING DIGRAMS FOR SISO Shift Register

RESULTS: Thus the SISO Shift Register using verilog and validating their functionality using their functional tables is implemented and verified.
