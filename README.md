# PUYA Projects
PUYA projects is an experiment to use low-cost ARM PUYA microcontrollers.

## Requirements
- PUYA microcontroller (We used a PUYA Dev Board with a PY32F002AA15M6TU microcontroller)
- J-Link Segger Debugger
- Visual Studio Code (mandatory)
- Git (Recommended)

## Tools Installation

1. **Install GNU Arm Embedded Toolchain:**
   - Download the appropriate version from [Arm GNU Toolchain Downloads](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads) (We use the v12.3 rel1).
   - Add the tool's binary directory to the Windows PATH.

2. **Open the Command Line**

3. **Verify GNU Toolchain Installation:**
In your Command Line verify if GNU Toolchain Installation was correct.
   ```powershell
   &"C:\Program Files (x86)\Arm GNU Toolchain arm-none-eabi\12.3 rel1\bin\arm-none-eabi-gcc" -v 

4.  **Install Make:**
    -   Download Make from [GnuWin](http://gnuwin32.sourceforge.net/packages/make.htm).
    -   Add Make to the environment variables.

5.  **Check Make Installation:**
     ```powershell
     make -v
    
5.  **Install SEGGER J-Link:**
    -   Download from [J-Link / J-Trace Downloads](https://www.segger.com/downloads/jlink).
    -   Install J-Link tools.

## Project Configuration

1.  **Clone the PY32 Examples Repository:**
    Copy code
    
    `git clone https://github.com/TDLOGY/py32f0-template-project` 
    
2.  **Copy the JLinkDevices Directory:** Copy `[PY32 Directory]/Misc/Flash/JLinkDevices` to `C:\Users\[User]\AppData\Roaming\SEGGER\JLinkDevices\`.
    
3.  **Open Visual Studio Code:**
    
    -   Open the `py32f0-template-project` folder.
4.  **Find the JLink Path:** Locate the path where JLink is installed, typically something like: `"C:\Program Files\SEGGER\JLink\JLink"`. Save it for future configurations.
    
5.  **Connect J-Link and Verify:** In Windows PowerShell, use the following command to verify the J-Link connection:
    
    powershellCopy code
    
    `&"C:\Program Files\SEGGER\JLink\JLink"` 
    
6.  **Compile the Project:** In the project folder, run:
    Copy code
    
    `make -j4` 
    
7.  **Adjust Makefile for Your Chip:** Edit the Makefile to change the chip reference to `"PY32F002AX5"`.
    
8.  **Modify the Code:**
    
    -   Open the `/User/main.c` file.
    -   Adjust pin references from ports B and F to A as needed.
9.  **Compile Again:** Run `make -j4` to compile with the changes made.
    
10.  **Program the Board:** Use `make flash` to upload the code to your board using J-Link.
    
11.  **Save Your Changes:** Remember to save the modified files before compiling.
    
12.  **Clean Previous Compilation:** If you make changes to the code, run `make clean` before compiling again.
    

PUYA Dev Board with the PY32F002AA15M6TU microcontroller should now be configured and ready to go!



## Maintainer

<a
href="https://github.com/sponsors/ElectronicCats">

<img  src="https://electroniccats.com/wp-content/uploads/2020/07/Badge_GHS.png"  height="104" />

</a>

Electronic Cats invests time and resources providing this open source design, please support Electronic Cats and open-source hardware by purchasing products from Electronic Cats!

[Agregando el link como referencia]: <https://github.com/ElectronicCats/Template-Project-KiCAD-CI>
