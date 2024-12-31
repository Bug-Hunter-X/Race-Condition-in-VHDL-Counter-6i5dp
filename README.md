# VHDL Counter Race Condition

This repository demonstrates a subtle race condition in a simple VHDL counter and provides a solution.

## The Bug

The `buggy_counter.vhdl` file contains a counter that increments on each rising clock edge and resets to 0 when the `rst` signal is high.  However, there is a race condition: if `rst` changes at the same time as the clock edge, the reset might be missed, leading to unpredictable behavior.

## The Solution

The `fixed_counter.vhdl` file provides a corrected implementation.  It uses a more robust reset mechanism to avoid the race condition, ensuring reliable counter operation regardless of the timing of the reset signal.

## How to Reproduce

1.  Simulate the `buggy_counter.vhdl` using your preferred VHDL simulator.
2.  Apply a reset signal that changes very close to a rising clock edge.
3.  Observe that the reset might not be effective.
4.  Simulate `fixed_counter.vhdl` to see the correct behavior.
