# Silicon From Scratch

![Single-Cycle CPU Architecture](single-cycle-cpu/docs/logo.jpg)

> An open, hands-on hub for learning how processors are *actually* built — from a single line of Verilog all the way to a physical layout.

---

<p align="center"><em>You don't learn to ride a bike by reading about it; you strap on your helmet and push off, finding your balance as you go, with hope that your leap into the unknown will take you to somewhere you couldn't have reached standing still.</em></p>

---

## What This Is

**Silicon From Scratch** is a learning hub for anyone curious about how the processors inside modern devices are designed and built — and who would rather build one than just read about it. It gathers working processor designs, the fundamental logic blocks they're made from, and the simulation and verification that proves they actually work, all in one place you can clone, run, and take apart.

The whole approach is built around one idea: **dive in.** You don't need a degree, an expensive software license, or anyone's permission to get started. Every core project here can be simulated on your own machine with free, open-source tools, and the material is written to be approachable for someone seeing it for the first time. Start with a single logic block, watch it come alive in a waveform, then climb your way up to a complete CPU.

## Who It's For

Students, hobbyists, career-switchers, tinkerers, and the merely curious — young or old. If you've ever wondered how a sliver of sand ends up running your code, this is for you. No prior chip-design experience is assumed; the projects are ordered so you can build understanding one layer at a time.

## Companion Website

This repository is paired with a companion website where the same material lives in a graphical, browsable setting — including **interactive learning content** designed to let you experiment with these concepts directly in your browser.

🔗 **[Silicon From Scratch Companion Website]([#](https://estaresinic05.github.io/silicon-from-scratch-site))**

Use the repo to read, clone, and run the real designs; use the website to explore the ideas visually and play with the interactive demos.

## Start Here

New to all of this? Work through the projects top to bottom. Each one assumes only what came before it.

| Project | Level | Status | What you'll build & learn |
|---------|-------|--------|---------------------------|
| [ALU](./ALU/) | Beginner — start here | Complete | A parameterized N-bit ripple-carry ALU (slice + MSB) supporting AND, OR, ADD, SUB, SLT, NOR, and NAND. The single best place to understand how arithmetic and logic are done in hardware. Verified against a behavioral oracle. |
| [Single-Cycle CPU](./single-cycle-cpu/) | Intermediate | Complete | A full RV32I single-cycle Harvard-architecture processor — datapath, control, register file, and memory working together to execute real RISC-V programs. Verified against a lockstep golden model and a hand-derived final-state oracle. |
| Pipelined CPU | Advanced | Planned | A 5-stage pipeline with hazard detection and forwarding — the leap from "it works" to "it works *fast*." |

## What You'll Find in Each Project

Every design is meant to be opened up and understood, not just run. For each one you'll find:

- **RTL** — synthesizable Verilog/SystemVerilog source for the datapath, control unit, register file, ALU, and memory subsystem. This is the design itself.
- **Testbenches** — self-checking verification environments, including lockstep golden-model comparison against independent reference simulators and hand-derived final-state oracles. This is how you *prove* a design is correct.
- **Waveforms** — VCD dumps and simulation traces that let you watch the design's behavior cycle by cycle. This is where the abstract becomes concrete.
- **Programs** — RISC-V machine-code test programs that exercise arithmetic, logic, memory, and control-flow instructions. This is what the CPU actually runs.

## Tools

You can run the core RTL projects with **free, open-source tools** — no licenses, no cost:

- **Icarus Verilog** — RTL simulation
- **GTKWave / EPWave** — waveform inspection

The advanced physical-design track uses the **Cadence suite** (Virtuoso, Spectre) for analog/mixed-signal and full-custom layout. That's the professional toolchain — useful to know it exists, but you don't need it to get started or to learn the fundamentals.

## Roadmap

This hub is actively growing. Planned additions include:

- **More interactive learning content** on the companion website, so concepts can be explored visually and experimented with directly.
- **Pipelined CPU** — the next major design (see the table above).
- **Physical design** — schematic capture, layout, and full-custom flows using the Cadence toolchain.
- **Transistor-level simulation** — verifying timing and functional behavior beyond the RTL abstraction.
- **Synthesis and timing analysis** — mapping RTL to gates and characterizing performance.

## Contributing & Collaborating

This started as one person's exploration, but the goal is for it to be useful to others. If you spot something confusing, find a bug, or want to add a clearer explanation, contributions and issues are welcome.

## About

I built these projects to deepen my own understanding of computer architecture and the complete digital design flow — from a line of Verilog to a physical layout. Along the way I realized the material I was creating could help anyone else curious about the field, which is what this hub is for. *(Recruiters and collaborators: this also serves as a portfolio of that work — feel free to explore any of the projects above.)*
