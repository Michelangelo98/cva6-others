This folder contains the src file modified 
from the master branch of the axi_riscv_atomics
repository. The patches were done for 
two reasons:
1)solve the absence of support for burst mode
that comes to errors when lr/sc instructions
are executed and the cacheline is bigger than
the axi data bus
2)avoid errors with questasim and Vivado