# PUYA Projects
PUYA projects is an experiment to use low-cost ARM PUYA microcontrollers.

## PY32F002A key features and specifications:

- MCU Core – 32-bit Arm Cortex-M0+ @ 24 MHz
- Memory – 3KB SRAM
- Storage – 20KB flash
- Peripherals:
  - 5 GPIOs (PF0, PA1, PA5, PA6, PA7)
  - 1x USART
  - 1x I2C, 1x SPI,  1x PWM (PA1 AF13 TIM1_CH4)
  - Up to 9-channel 12-bit ADC
- Timers
  - 1x general-purpose 16-bit timers
  - 1x 16-bit advanced control timer
  - 1x low-power timer (LPTIM) to support wake-up from stop mode
  - 1x SysTick timer
  - 1x watchdog timers (IWDT)
- Clocks
  - 4/24MHz RC (HSI)
  - 32.768KHz RC (LSI)
  - 4~24MHz HSE (External crystal oscillator)
  - Supply Voltage – 1.7V to 5.5V DC
  - Packages – SOP8 (4.9×3.7×1.75 mm), SOP16, ESSOP10, TSSOP20
  - Temperature Range – – 40°C to +85°C

## FOR WINDOWS
## Requirements
- PUYA microcontroller (We used a PUYA Dev Board with a PY32F002AA15M6TU microcontroller)
- J-Link Segger Debugger
- Visual Studio Code (mandatory)
- Git (Recommended)

## Tools Installation
1. **Install GNU Arm Embedded Toolchain:**
   - Download the appropriate version from [Arm GNU Toolchain Downloads](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads) (We use arm-none-eabi v12.3 rel1).
   - Add the tool's binary directory to the Windows PATH.

   To add the environment variable we look in the windows bar: "Edit environment variables for your account".

<p align="center">
   <img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/2b9cfc7f-a8c1-4389-b5f6-4fe8a261558a" height="100" />
   <div align="center">
      <sup><sub>Open "Edit environment variables for your account".</sub></sup>
   </div>
 </p>
    
 <p align="center">
    <img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/a1d49e67-5ad8-4e1b-a387-8bf3bbd77506" height="350" />
    <div align="center">
      <sup><sub>Open "Environment Variables...".</sub></sup>
    </div>
 </p>

<p align="center">
    <img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/3e97e27f-15d1-41a7-aba7-faefe7543999" height="200" />
   <div align="center">
      <sup><sub>Select "Path" and then "Edit...".</sub></sup>
    </div>
 </p>

 <p align="center">
    <img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/de063c06-850a-42ae-a969-8e72f928644e" height="350" />
   <div align="center">
      <sup><sub>Add "New" variable and add the path: "C:\Program Files (x86)\Arm GNU Toolchain arm-none-eabi\12.3 rel1\bin".</sub></sup>
    </div>
 </p>

2. **Open the Command Line:**
To open the "Command Line" search "cmd" or "PowerShell" in your windows bar. In this case "Windows PowerShell" was used, and a window like the following should open:
<p align="center">
   <img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/3f7d9ee9-3b99-4c0c-ba8a-25971affb48a" height="350" />
 </p>

3. **Verify GNU Toolchain Installation:**
In your Command Line verify if GNU Toolchain Installation was correct.
   ```powershell
   &"C:\Program Files (x86)\Arm GNU Toolchain arm-none-eabi\12.3 rel1\bin\arm-none-eabi-gcc" -v 
   ```
   If it has been installed correctly you should obtain a result similar to the following:
<p align="center">
  <img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/de64e456-4086-4c73-be45-b424a11bfee0" height="350" />
 </p>

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
    
3. **Find the JLink Path:** Locate the path where JLink is installed, typically something like: `"C:\Program Files\SEGGER\JLink\JLink"`. Save it for future configurations.

4.  **Connect J-Link and Verify:** In Windows PowerShell, use the following command to verify the J-Link connection:
    
    ```powershell
       &"C:\Program Files\SEGGER\JLink\JLink"
    ```

5.  **Open Visual Studio Code:**

    -   Open the `py32f0-template-project` folder.
    
6.  **Adjust Makefile for Your Chip** (The "Makerfile" is located in the project folder):

<p align="center">
   <img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/bfe788a8-2e78-49db-9450-0b84e4ba5ffb" height="350" />
   <div align="center">
      <sup><sub>Located in the project folder.</sub></sup>
   </div>
 </p>
   <ul>
      <ul>
         <li>Edit the Makefile to change the tools references, it uses the path references of the previously installed tools.</li>
      </ul>
   </ul> 

<p align="center">
   <img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/551f3017-d589-43ff-ab84-0dcf48a5dac5" height="250" />
   <div align="center">
      <sup><sub>Tools references.</sub></sup>
   </div>
 </p>

   <ul>
      <ul>
         <li>Edit the Makefile to change all the chip reference to `"PY32F002AX5"`.</li>
      </ul>
   </ul> 
    
7.  **Compile the Project:**
   
    -   In Visual Studio Code open a terminal.

<p align="center">
   <img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/7ce44823-d533-45d1-a0cc-4d1285550cf6" />
   <div align="center">
      <sup><sub>Opening a Terminal.</sub></sup>
   </div>
 </p>


  <ul>
      <ul>
         <li> Execute: <code> make -j4 </code> in the Visual Studio Code (VSC) terminal and verify that it compiles correctly, otherwise, it could be that the "Makefile" has not been configured correctly.</li>
      </ul>
   </ul>  

8.  **Modify the Code:**
    -   Open the `/User/main.c` file.
    -   Adjust pin references from ports B and F to A as needed.
  
9.  **Compile Again:** Execute `make clean` to clean the compilation and after `make -j4` to compile with the changes made.
    
10.  **Program the Board:** Use `make flash` to upload the code to your board using J-Link. (You must have your J-Link connected to your computer and with the corresponding connections to the development board)
    
11.  **Save Your Changes:** Remember to save the modified files before compiling.
    
12.  **Clean Previous Compilation:** If you make changes to the code, run `make clean` before compiling again.

PUYA Dev Board with the PY32F002AA15M6TU microcontroller should now be configured and ready to go!

**The development board can be programmed via SWD by a J-Link** (The J-link connections will depend on which J-Link and connector you are going to use).

### What is SWD?
SWD is a bidirectional communication protocol that allows for fast and efficient microcontroller debugging and programming.

SWD uses two signal lines, one for data (SWDIO) and one for clock (SWCLK), to communicate with the microcontroller. Through these lines, you can load programs into the microcontroller, stop code execution to inspect variables and debug errors, and perform other debugging operations. It is faster and more efficient than older debugging methods, such as JTAG.

## J-Link Connections to the Dev Board
As mentioned earlier, SWD communication involves two key lines: **SWDIO** for data and **SWCLK** for the clock signal. However, in addition to these two lines, we also require two more connections:

- **GND (Ground)**: This connection is essential to establish a common reference point for electrical potential and ensure proper communication.
- **VRef (Voltage Reference)**: In this case, our PUYA Dev board works with a logical voltage level of 3.3V so it is necessary to provide this voltage to the J-Link tool. This voltage, known as VRef, is necessary to support the communication between the J-Link and the target board.

**Note:** You need to power up the PUYA Dev board with an external 5V power supply.

### Instructions to use the J-Link PLUS Compact
To program the PUYA Dev Board with the J-Link PLUS Compact we will need the following components:
<div align="center">
   <table>
        <tr>
           <td><img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/4b504111-3aa9-455b-9088-e81335c9b060" alt="Imagen 0" height= 250>  
               <div align="center"><sup><sub>USB Cable.</sub></sup></div>
            </td>
            <td><img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/0aea4d75-74ab-48bc-a515-7fd1c19c8f10" alt="Imagen 1" height= 250>
               <div align="center"><sup><sub>J-Link PLUS Compact.</sub></sup></div>
            </td>
           <td><img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/3a7c5ae6-9633-4773-86f2-8364864c8ce5" alt="Imagen 2" height= 250>
               <div align="center"><sup><sub>Dupont Wires.</sub></sup></div>
            </td>
        </tr>
   </table>
</div>

In addition to this, in order to make the connections we must know what the J-Link pinout is, take the image below as a reference and connect each wire from your PUYA Dev Board to the corresponding one on the J-Link:
<p align="center">
   <img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/2c44cddc-163c-4924-840f-2b99760bbca3" height="250"/>
   <div align="center">
      <sup><sub>J-Link PLUS Compact connector.</sub></sup>
   </div>
 </p>

### Instructions to use the J-Link EDU Mini:
To program the PUYA Dev Board with the J-Link EDU Mini we will need the following components:
<div align="center">
   <table>
        <tr>
           <td><img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/4b504111-3aa9-455b-9088-e81335c9b060" alt="Imagen 0" height= 250>  
               <div align="center"><sup><sub>USB Cable.</sub></sup></div>
            </td>
            <td><img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/8adad6ce-d872-43f5-882f-62f0f1e7ed49" alt="Imagen 1" height= 250>  
               <div align="center"><sup><sub>J-Link EDU Mini.</sub></sup></div>
            </td>
           <td><img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/3684a6df-3576-4cc1-adb4-5092f04cea77" alt="Imagen 2" height= 250>
               <div align="center"><sup><sub>J-Link EDU Mini PCB Adapter.</sub></sup></div>
            </td>
            <td><img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/53cdcef2-9105-4639-8583-adb38de6cc1f" alt="Imagen 3" height= 250>
               <div align="center"><sup><sub>J-Link EDU Mini Cable.</sub></sup></div>
            </td>
           <td><img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/3a7c5ae6-9633-4773-86f2-8364864c8ce5" alt="Imagen 2" height= 250>
               <div align="center"><sup><sub>Dupont Wires.</sub></sup></div>
            </td>
        </tr>
   </table>
</div>

As shown in the required material, the J-Link EDU Mini PCB Adapter helps us a lot in identifying where we need to connect each wire from our PUYA development board to the PCB adapter. After connecting the corresponding wires you can program your board.

### Connection example:
<p align="center">
   <img src="https://github.com/ElectronicCats/puya-projects/assets/44976441/0281e9c8-cc55-4ca9-a878-a3433ce1341b" height= 500>
   <div align="center">
      <sup><sub>Illustrative image of connections.</sub></sup>
   </div>
 </p>

The image above is just a reference image of the connections.
The board is being powered directly with 5V and there are the following connections:
<div align="center">
   <table>
      <tr>
       <th>PUYA Dev Board</th>
       <th>J-Link Compact</th>
       <th>J-Link EDU</th>
       <th>Power Supply</th>
     </tr>
     <tr>
       <td>3.3V</td>
       <td>VTref</td>
       <td>Vref</td>
       <td>X</td>
     </tr>
     <tr>
       <td>GND</td>
       <td>GND</td>
       <td>GND</td>
       <td>GND</td>
     </tr>
     <tr>
       <td>DIO</td>
       <td>SWDIO</td>
       <td>SWIO</td>
       <td>X</td>
     </tr>
     <tr>
       <td>CLK</td>
       <td>SWCLK</td>
       <td>CLK</td>
       <td>X</td>
     </tr>
     <tr>
       <td>5V</td>
       <td>X</td>
       <td>X</td>
       <td>5V</td>
     </tr>
   </table>
</div>

## Thanks / Contributors
This example is based on the [Example Code PY32F0](https://github.com/TDLOGY/py32f0-template-project/tree/618b7ab8a95be73d5871b39afd02e14fb6a823dd)

## Maintainer

<div align="center">
   <a href="https://github.com/sponsors/ElectronicCats" >
      <img  src="https://electroniccats.com/wp-content/uploads/2020/07/Badge_GHS.png"  height="104" />
   </a>
</div>
Electronic Cats invests time and resources providing this open source design, please support Electronic Cats and open-source hardware by purchasing products from Electronic Cats!

[Agregando el link como referencia]: <https://github.com/ElectronicCats/Template-Project-KiCAD-CI>
