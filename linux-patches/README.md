Several patches were added to linux starting 
from https://github.com/openhwgroup/cva6-sdk/tree/v0.3.0-op.
Three file were modified:

head.S:
fence added at line 147 to remove the data race between
the parking loop of the waiting core and the boot core
which modify the value pointed by the sp

compiler.h:
fence added at the end of the WRITE_ONCE macro and 
ate the beginning of the READ_ONCE macro


processor.h:
fence added at the beginning of cpu_relax() and  wait_for_interrupt()
to flush the cache before starting to wait