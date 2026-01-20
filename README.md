### My Own Linux Shell

This project contains a custom implementation of a functional shell that manages I/O redirection and job control, supporting both foreground and background task execution. The objective was to manage process lifecycles and inter-process communication through the Linux signaling model. The system implements a complete job control interface including built-in commands for quit, jobs, bg, and fg. It adheres to strict async-signal-safety standards and utilizes process group synchronization to manage terminal interrupts.

#### Performance Data

* Passed evaluation using a suite of 32 trace files and a reference shell comparison utility
* Implemented fork-exec models to prevent signal leakage to the parent shell
* Correctly reaped all zombie children
* Eliminated race conditions in job list access, avoiding busy-waiting or CPU cycle waste
* Verified functional input and output redirection, including concurrent redirection of both standard streams

#### Development and Tools

* Language: C
* Platform: Linux x86-64
* Infrastructure: CS:APP library (provides the SIO series of functions)
  
#### Academic Integrity Statement

In compliance with Carnegie Mellon University academic integrity policies, the source code for this project is maintained in a private repository. I am available to discuss the specific data points, performance results, and engineering trade-offs encountered during the development of this shell.
