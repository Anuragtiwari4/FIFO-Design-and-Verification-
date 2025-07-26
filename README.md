# FIFO Design and Verification

## Overview
This project implements a **FIFO (First-In-First-Out) buffer** in **SystemVerilog**, along with a **constrained random testbench** built using SystemVerilog OOP concepts.  

It showcases **RTL design + functional verification** skills by combining hardware modeling and advanced testbench techniques.

---

## Project Architecture

### 1. FIFO RTL Design (`design.sv`)
- **Width:** 8 bits  
- **Depth:** 16 entries  
- **Features:**
  - Synchronous FIFO with `clk` & `rst`
  - Write (`wr`) and Read (`rd`) operations
  - `full` & `empty` status flags
  - Internal pointers (`wptr`, `rptr`) with an occupancy counter
  - Simple, synthesizable RTL

 **Why FIFO?**  
FIFO buffers are widely used in **data buffering, clock domain crossing, network-on-chip communication, and SoC designs**.

---

### 2. Constrained Random Testbench (`testbench.sv`)
Implements a **SystemVerilog OOP-based verification environment**:

- **Transaction Class**
  - Randomizes read/write operations (`oper`)  
  - Constrained to generate a balanced mix of reads & writes  

- **Generator Class**
  - Produces multiple random transactions  
  - Uses a `mailbox` for synchronization  

- **Driver & Monitor**
  - Driver applies stimuli to the DUT  
  - Monitor captures DUT responses  

- **Scoreboard**
  - Checks FIFO data correctness  

**Key Verification Techniques Used:**
- Constrained random stimulus generation  
- Mailbox for thread-safe communication  
- Events for synchronization (`next`, `done`)  
- Layered testbench structure (Generator → Driver → DUT → Monitor → Scoreboard)

This approach is similar to a **UVM-lite verification methodology**, demonstrating strong verification skills.


