1. Can everything be done using asm and not direct assembly?
2. For the page tables associated with each process, do we store it in the pmap structure along with the OS memory or in the backstore?
3. If the page table is too long, does it also get paged or stored in the backstore?
4. Expanding on question one, can we use simple C pointers to have fixed hardcoded adresses for the datastructures we need? THat is say all page tables of a specific process have to be loaded at memory address A.
5. Can virtual processes access normal memory? 
6. Will there be dynamic allocations such that the page table might be changed?