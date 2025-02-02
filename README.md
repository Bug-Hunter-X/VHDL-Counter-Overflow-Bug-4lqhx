# VHDL Counter Overflow Bug

This repository demonstrates a common bug in VHDL: counter overflow.  The provided VHDL code implements a simple counter, but lacks proper handling for overflow conditions. When the counter reaches its maximum value (15), the next increment will cause an unexpected wrap-around to 0.

## Bug Description

The `counter` entity is designed to count from 0 to 15.  However, if the clock continues to pulse after reaching 15, the counter will increment beyond its defined range (0 to 15), which leads to an overflow and undefined behavior.  This can cause unexpected behavior in the system and requires a more robust solution.

## Solution

The solution addresses the overflow issue by adding a check to prevent the counter from incrementing beyond the maximum value.  Instead of wrapping around, the counter will stop at the maximum value. This ensures predictable behavior and prevents unexpected system disruptions.

## How to reproduce the bug

1. Simulate the `counter_bug.vhdl` code.
2. Observe the output `count` signal.  Note that when the counter reaches 15, it increments back to 0 on the next clock cycle. 

## How to fix the bug

1. Replace `counter_bug.vhdl` with `counter_solution.vhdl`.
2. Re-simulate the corrected code.
3. Observe that the `count` signal will stop at 15 and no longer wraps around.