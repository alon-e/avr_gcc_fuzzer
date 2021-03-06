

# AVR-GCC bug seeker

an interactive tool for testing avr C tools
 
## avr analyzer src files:
AVR-GCC bug seeker - an interactive tool for testing avr C tools

### console.py:
an all in one interface for AVR-GCC bug seeker.


# Console Commands
|Console|Commands|Available:|
|---|---|---
|EOF                      |compile_run_gcc  |help                    
|catagorize_failedCFiles  |exit             |lineChooser_failedCFiles
|catagorize_specific      |flow_run_inf     |lineChooser_specific    
|compile_run_arduino      |flow_run_n       |shell                   
|compile_run_avr          |flow_run_once    ||



## flow.py:
this file holds the functionality of the basic bug finding,
it generates the code using csmith, then compiles and runs
(using utility functions) then compares the results and 
saves the code if a bug is found.

## command.py:
in order to keep the flow running despite the infinite loops
that generated programs some times produce, using command.py 
times the simulation (to take no more than 10 seconds) and 
aborts if it gets stuck.

## addprints.py:
uses pycparser to insert debug prints automatically, adds a
print for each assignment in the code, to print the checksum
and the id of the assignment line in the original source file.

## lineChooser.py:
periodically takes a c file that has been found to have a bug
and chooses the line in which the bug first appeared. to do so
it uses utility functions and its own compare function.

## categorize.py:
creates a minority report for failed c files.

## util.py:
utility functions such as compile file, run file and run command.

## settings.py:
the parameters file for all other files.
