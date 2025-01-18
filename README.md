# VHDL Process Sensitivity List Bug
This repository demonstrates a common error in VHDL: incorrect process sensitivity lists.  Improperly specifying the signals a process is sensitive to can lead to unexpected behavior and difficult-to-debug issues. 

The `bad_process.vhdl` file contains code that exhibits this problem.  The `good_process.vhdl` file demonstrates the correct way to write the process.

**Bug:**
The `bad_process.vhdl` process only uses `clk` in the sensitivity list. It should also include `data_in`. This means that changes to `data_in` won't immediately be reflected in `data_out` because the process won't trigger on those changes.

**Solution:**
The `good_process.vhdl` demonstrates the corrected code where the sensitivity list includes both `clk` and `data_in`. Now, changes to `data_in` are correctly reflected in `data_out` on the next clock edge.

This demonstrates the importance of carefully considering all signals that may affect the process's output.