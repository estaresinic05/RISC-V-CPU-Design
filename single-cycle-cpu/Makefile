#*******************************************************
# Project:        RISC-V CPU Design
# Module:         Makefile
# Author:         Elliot Staresinic
# Date:           2026-06-01
#
# Description:
#   This Makefile compiles the Single Cycle CPU 
#   hierarchy into a file called 'sim', which can be ran
#   by issuing the command 'vvp sim'. Alternatively,
#   issuing the command 'make run' will compile and run
#   the program. In order to view the output waveform,
#   the command 'gtkwave waveform/dump.vcd' must be issued.
#
#*******************************************************

SIM  = sim
STD  = -g2012

TB   = testbench/tb_sc_cpu_top_level.v

SRCS = rtl/sc_cpu_top_level.v \
       rtl/sc_cpu_datapath.v \
       rtl/sc_cpu_control.v \
       rtl/alu_control.v \
       rtl/alu_full.v \
       rtl/alu_msb.v \
       rtl/alu_slice.v \
       rtl/full_adder.v \
       rtl/ripple_carry_adder.v \
       rtl/reg_file.v \
       rtl/imm_gen.v \
       rtl/instruct_mem.v \
       rtl/data_mem.v \
       rtl/mux_2x1.v \
       rtl/mux_4x1.v

# ---- OS detection ------------------------------------------
ifeq ($(OS), Windows_NT)
    RM = del /Q
else
    RM = rm -f
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
	$(RM) $(SIM) dump.vcd

.PHONY: all run clean
