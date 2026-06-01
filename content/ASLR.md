ASLR (address space layout randomisation) is a [[Linux]] feature to prevent [[Buffer overflow]] attacks.

When a process is launched, ASLR randomizes the memory addresses of:

- The executable
- Libraries
- The [[Stack]]
- The [[Heap]]

This feature also exists for the kernel, known as KASLR.

However this only works for PIE (position-independent executables).

This mechanism can be circumvented if addresses can be leaked, for example through unsanitized calls to `sprintf`.
