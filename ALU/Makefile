#*******************************************************
# Project:        RISC-V CPU Design
# Module:         Makefile
# Author:         Elliot Staresinic
# Date:           2026-06-02
#
# Description:
#   This Makefile compiles the ALU hierarchy into a file
#   called 'sim', which can be ran by issuing the command
#   'vvp sim'. Alternatively, issuing the command 'make run'
#   will compile and run the testbench. In order to view the
#   output waveform, the command 'gtkwave waveforms/dump.vcd'
#   must be issued.
#
#*******************************************************

SIM  = sim
STD  = -g2012

TB   = testbench/tb_alu_full.v

SRCS = rtl/alu_full.v \
       rtl/alu_msb.v \
       rtl/alu_slice.v \
       rtl/full_adder.v \
       rtl/mux_2x1.v \
       rtl/mux_4x1.v

# ---- OS detection ------------------------------------------
ifeq ($(OS), Windows_NT)
    RM  = del /Q
    VCD = waveforms\dump.vcd
else
    RM  = rm -f
    VCD = waveforms/dump.vcd
endif

# ---- default target (compile only) -------------------------
all: $(SIM)

$(SIM): $(TB) $(SRCS)
	iverilog $(STD) -o $(SIM) $(TB) $(SRCS)

# ---- run ---------------------------------------------------
run: $(SIM)
	vvp $(SIM)

# ---- clean -------------------------------------------------
clean:
	$(RM) $(SIM) $(VCD)

.PHONY: all run clean
