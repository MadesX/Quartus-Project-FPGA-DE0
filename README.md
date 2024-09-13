# Quartus-Project
**This project was made for FPGA - DE0**  
Quartus Project implementing a system which uses different switches (SW) to activate various components : Stopwatch, Timer, Clock, MiniGame, Calculator.  
Each component is operated through a set of buttons that allow control over starting, stopping, and resetting functions.  
This project was made using Quartus schematic design and SystemVerilog.

# Project Overview
This project implements a multi-functional digital system designed to perform various tasks such as timing, calculating, and simple gaming. The system consists of five main components: a stopwatch, a timer, a clock, a mini-game, and a calculator. Each component can be activated using dedicated switches, and controlled through buttons on the board. The project is written in SystemVerilog and provides a visual interface using LEDs and seven segments to display different states and results.

# Components Overview

**1. Stopwatch**

The stopwatch supports up to four players, each able to record and view their own time.  

   * **Activation:**  
     Set SW[9] to 1.
     
   * **Controls:**  
        Start/stop with button2, reset with button0.  
        View times for each player using SW[1] to SW[4].  
        Save player time by switching to its view mode and using button1.
     
   * **Viewing Modes:**  
        Mode 1 (SW[0] = 1): Display milliseconds and seconds.  
        Mode 2 (SW[0] = 2): Display minutes and hours.  

**2. Timer**

The timer allows users to set a countdown for hours, minutes, and seconds.  
During initial activation we must set the timer by selecting hours, minutes and seconds (in that order).  

  * **Activation:**  
    Set SW[8] to 1.
    
  * **Controls:**  
        Set hours, minutes, and seconds using button2 and confirm with button1.  
        Start/stop with button2, reset with button0.  
        The current timer stage is shown on LEDG[1..0] in binary.
    
   * **Viewing Modes:**  
        Mode 1 (SW[0] = 1): Display milliseconds and seconds.  
        Mode 2 (SW[0] = 2): Display minutes and hours.  

**3. Clock**

The clock allows users to set time and view it in different formats.  
During initial activation we must set the clock by selecting hours, minutes and seconds (in that order).  

  * **Activation:**  
    Set SW[7] to 1.  
    
  * **Controls:**  
        Set hours, minutes, and seconds using button2, and confirm with button1.  
        Start with button2, reset with button0.  
        The current clock stage is indicated by LEDG[1..0] in binary format.  
    
  * **Viewing Modes:**  
        Mode 1 (SW[0] = 1): Display milliseconds and seconds.  
        Mode 2 (SW[0] = 2): Display minutes and hours.  

**4. Mini-Game**  

A fast-paced game where the player attempts to stop a rapidly increasing counter between specific values.

  * **Activation:**  
    Set SW[6] to 1.  
    
  * **Game Objective:** Stop the counter between 50 and 55, use button0 to stop. 
    
  * **Success Indicator:** LEDG[6..0] will blink if the player stops the count in the correct range.  
    
  * **Reset:** Use button0 to reset the game.  

**5. Calculator**  

A simple calculator that performs both arithmetic and bitwise operations on two 4-bit numbers.  
First an operation is needed to be selected by its number, than the 1st number, the 2nd number and than the result will be shown.

  * **Activation:**  
    Set SW[5] to 1.  
    
  * **Supported Operations:**  
        0 - Addition  
        1 - subtraction  
        2 - multiplication  
        3 - division  
        4 - modulo  
        5 - bitwise AND  
        6 - bitwise OR  
        7 - bitwise XOR  
        The result of bitwise operations is also displayed on LEDG[3..0].  
    
  * **Error Handling:** Displays "E" in case of division by zero or negative results from subtraction.  
    
  * **Controls:**  
        Select operations with switches, perform actions using button2 and confirm and continue with button1.  
        Reset the calculator with button0.  

**Note:** The calculator functionality is written in SystemVerilog.

# Usage Instructions

  * Open and extract the .qar file using Quartus and load it into your board.
  * Use the switches (SW) to activate the desired component.
  * Use the buttons (button0, button1, button2) to interact with each component according to the controls specified above.
  * View outputs and results using the LEDs (LEDG) and the Seven Segments.

# Requirements

  * SystemVerilog compatible hardware.
  * FPGA or similar development board, preferably FPGA - DE0.
