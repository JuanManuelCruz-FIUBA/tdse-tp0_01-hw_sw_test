# FIUBA - Electrónica - Taller de Sistemas Embebidos
## Trabajo Práctico N°: 0 - Proyecto N°: 01 - Primer Proyecto

### Board: NUCLEO-F103RB

<details>
<summary>IDE: STM32CubeIDE Version: 1.7.0 & 1.13.2</summary>

* Connet **NUCLEO-F103RB** board to PC
  * Execute **STM32CubeIDE**
    * **File** (Alt+Shift+N) => **New** => **STM32 Project**
      * **BOARD Selector** Commercial Part Number: **NUCLEO-F103RB** => **Select** => **Next**
	* **Project Name**: **tdse-tp0_01-hw_sw_test** => **Next** => **Finish**
	  * **Board Project Options**: Initialize all peripherals with their default Mode ? => **Yes**
    * **Project Explorer**:
      * **tp0_01_hw-sw-test** => **Core** => **Src** => **main.c** => 
        * Find the comment:
          ```C
          /* USER CODE BEGIN 3 */
          ```
        * Copy and paste the following code into the **next line** (following the comment):
          ```C
          HAL_GPIO_TogglePin(LD2_GPIO_Port, LD2_Pin);
          HAL_Delay(500);
          ```
        * **Save(Ctrl+S)** => **tp0_01_hw-sw-test** => **Build Project**
	  * **Console**:
          ```Console
          arm-none-eabi-size   tp0_01_hw-sw-test.elf
          	text	data	bss	dec	hex	filename
          	5676	20	1636	7332	1ca4	tp0_01_hw-sw-test.elf
          Finished building: default.size.stdout
          Finished building: tdse-tp0_01-hw_sw_test.bin
          Finished building: tdse-tp0_01-hw_sw_test.list
          	hh:mm:ss Build Finished. 0 errors, 0 warnings. (took Xs.YYYms)
          ```
      * **Bulid Analyzer**:
          ```Console
          Memory Regions:
		Region	Start addr	End addr	Size	Free		Used	Usage (%)
		RAM	0x20000000	2x20005000	20 KB	18,39 KB	1,61 KB	8,05%
		FLASH	0x08000000	0x08010000	128 KB	122,44 KB	5,56 KB	4,35%
          ```
      * **Debug**:
        * **tp0_01_hw-sw-test** => **Debug As** => **1 STM32 C/C++ Application** => **Debugger** =>
	  **Debug probe** => **ST-LINK (ST-LINK GDB server)** => **Apply** => **OK**
          * Confirm Perspective Switch => **Switch**
          * **Step Over (F6)** / **Resume (F8)** / **Suspend**
          * **...**
        * **tp0_01_hw-sw-test** => **Terminate and Remove** => **Yes**

* **GitHub**
  * **Repositories** => **New** =>
    * Repository name: **tdse-tp0_01-hw_sw_test**
    * Description: **FIUBA - Electrónica - Taller de Sistemas Embebidos - Trabajo Práctico N°: 0 - Proyecto N°: 01**
    * => **Create repository**

* **Git Bash**
  ```
  git init
  git branch -M main
  git remote add origin https://github.com/Username/tdse-tp0_01-hw_sw_test.git

  git status
  git add --all
  git commit -m "first commit"
  git push -u origin main
  ```
</details>

---
### Board: Blue Pill Original (uC: STM32F103C8)

<details>
<summary>IDE: STM32CubeIDE Version: 1.7.0</summary>

* Connet **Blue Pill Original** board to PC
  * Execute **STM32CubeIDE**
    * **Help** => **ST-Link Upgrade** => **Refresh device list** => **Open in upgrade mode** => **Upgrade** => **Cerrar** 
    * **File** (Alt+Shift+N) => **New** => **STM32 Project**
      * **MCU/MPU Selector** Commercial Part Number: **STM32F103C8** => **Select** => **Next**
	* **Project Name**: **tdse-tp0_01-hw_sw_test** => **Next** => **Finish**
	  * **Board Project Options**: Initialize all peripherals with their default Mode ? => **Yes**
    * **Pinout & Configuration**
      * **Categories**
        * **System Core**
          * RRC: **Mode and Configuration**
            * HSE: **Crystal/Ceramic Resonator**
            * LSE:  **Disable**
            * **Save(Ctrl+S)** => Do you want generate Code? => **Yes** => This action can be associated with C/C++ perspective. Do you want to open this perspective now? => **No**
            * SYS: **Mode and Configuration**
              * Debug: **SerialWire**
	      * Timebase Source: **SysTick**
              * **Save(Ctrl+S)** => Do you want generate Code? => **Yes** => This action can be associated with C/C++ perspective. Do you want to open this perspective now? => **No**
            * GPIO: **Mode and Configuration** (Pinout view: PC13: GPIO_Output)
              * GPIO: **Configuration**
                * outputl level: **High**
                * mode: **Output Push Pull**
		* Pull-up/Pull-down: **Pull-up**
                * Maximum output speed:	**Low**
                * User Label: **LED**
                * **Save(Ctrl+S)** => Do you want generate Code? => **Yes** => This action can be associated with C/C++ perspective. Do you want to open this perspective now? => **No**

    * **Clock Configuration**
      * PLL Source Mux: **HSE**
        * *PLLMuL: **x9**
          * System Clock Mux: PLLCLK => SYSCLK(MHz): **72M**
            * APB1 Prescaler: **/2** => PCLK1: **36**
          * **Save(Ctrl+S)** => Do you want generate Code? => **Yes** => This action can be associated with C/C++ perspective. Do you want to open this perspective now? => **Yes**

    * **Project Explorer**:
      * **tp0_01_hw-sw-test** => **Core** => **Src** => **main.c** => 
        * Copy and paste the following code on **line # 99**:
          ```C
          HAL_GPIO_TogglePin(LED_GPIO_Port, LED_Pin);
          HAL_Delay(500);
          ```
        * **Save(Ctrl+S)** => **tp0_01_hw-sw-test** => **Build Project**
	  * **Console**:
          ```Console
          arm-none-eabi-size   tp0_01_hw-sw-test.elf
          	text	data	bss	dec	hex	filename
          	4672	20	1572	6260	1874	tp0_01_hw-sw-test.elf
          Finished building: default.size.stdout
          Finished building: tdse-tp0_01-hw_sw_test.bin
          Finished building: tdse-tp0_01-hw_sw_test.list
          	hh:mm:ss Build Finished. 0 errors, 0 warnings. (took Xs.YYYms)
          ```
      * **Bulid Analyzer**:
          ```Console
          Memory Regions:
		Region	Start addr	End addr	Size	Free		Used	Usage (%)
		RAM	0x20000000	2x20005000	20 KB	18,45 KB	1,55 KB	7,73%
		FLASH	0x08000000	0x08010000	64 KB	59,42 KB	4,58 KB	7,15%
          ```
      * **Debug**:
        * **tp0_01_hw-sw-test** => **Debug As** => **1 STM32 C/C++ Application** => **Debugger** =>
	  **Debug probe** => **ST-LINK (ST-LINK GDB server)** => **Apply** => **OK**
          * Confirm Perspective Switch => **Switch**
          * **Step Over (F6)** / **Resume (F8)** / **Suspend**
          * **...**
        * **tp0_01_hw-sw-test** => **Terminate and Remove** => **Yes**

* **GitHub**
  * **Repositories** => **New** =>
    * Repository name: **tdse-tp0_01-hw_sw_test**
    * Description: **FIUBA - Electrónica - Taller de Sistemas Embebidos - Trabajo Práctico N°: 0 - Proyecto N°: 01**
    * => **Create repository**

* **Git Bash**
  ```
  git init
  git branch -M main
  git remote add origin https://github.com/Username/tdse-tp0_01-hw_sw_test.git

  git status
  git add --all
  git commit -m "first commit"
  git push -u origin main
  ```
</details>

---
### Board: Blue Pill Clone (uC: CH32F103C8)

<details>
<summary>IDE: STM32CubeIDE Version: 1.7.0</summary>

* Connet **Blue Pill Original** board to PC
  * Execute **STM32CubeIDE**
    * **Help** => **ST-Link Upgrade** => **Refresh device list** => **Open in upgrade mode** => **Upgrade** => **Cerrar** 
    * **File** (Alt+Shift+N) => **New** => **STM32 Project**
      * **MCU/MPU Selector** Commercial Part Number: **STM32F103C8** => **Select** => **Next**
	* **Project Name**: **tdse-tp0_01-hw_sw_test** => **Next** => **Finish**
	  * **Board Project Options**: Initialize all peripherals with their default Mode ? => **Yes**
    * **Pinout & Configuration**
      * **Categories**
        * **System Core**
          * RRC: **Mode and Configuration**
            * HSE: **Crystal/Ceramic Resonator**
            * LSE:  **Disable**
            * **Save(Ctrl+S)** => Do you want generate Code? => **Yes** => This action can be associated with C/C++ perspective. Do you want to open this perspective now? => **No**
            * SYS: **Mode and Configuration**
              * Debug: **SerialWire**
	      * Timebase Source: **SysTick**
              * **Save(Ctrl+S)** => Do you want generate Code? => **Yes** => This action can be associated with C/C++ perspective. Do you want to open this perspective now? => **No**
            * GPIO: **Mode and Configuration** (Pinout view: PC13: GPIO_Output)
              * GPIO: **Configuration**
                * outputl level: **High**
                * mode: **Output Push Pull**
		* Pull-up/Pull-down: **Pull-up**
                * Maximum output speed:	**Low**
                * User Label: **LED**
                * **Save(Ctrl+S)** => Do you want generate Code? => **Yes** => This action can be associated with C/C++ perspective. Do you want to open this perspective now? => **No**

    * **Clock Configuration**
      * PLL Source Mux: **HSE**
        * *PLLMuL: **x9**
          * System Clock Mux: PLLCLK => SYSCLK(MHz): **72M**
            * APB1 Prescaler: **/2** => PCLK1: **36**
          * **Save(Ctrl+S)** => Do you want generate Code? => **Yes** => This action can be associated with C/C++ perspective. Do you want to open this perspective now? => **Yes**

    * **Project Explorer**:
      * **tp0_01_hw-sw-test** => **Core** => **Src** => **main.c** => 
        * Copy and paste the following code on **line # 99**:
          ```C
          HAL_GPIO_TogglePin(LED_GPIO_Port, LED_Pin);
          HAL_Delay(500);
          ```
        * **Save(Ctrl+S)** => **tp0_01_hw-sw-test** => **Build Project**
	  * **Console**:
          ```Console
          arm-none-eabi-size   tp0_01_hw-sw-test.elf
          	text	data	bss	dec	hex	filename
          	4672	20	1572	6260	1874	tp0_01_hw-sw-test.elf
          Finished building: default.size.stdout
          Finished building: tdse-tp0_01-hw_sw_test.bin
          Finished building: tdse-tp0_01-hw_sw_test.list
          	hh:mm:ss Build Finished. 0 errors, 0 warnings. (took Xs.YYYms)
          ```
      * **Bulid Analyzer**:
          ```Console
          Memory Regions:
		Region	Start addr	End addr	Size	Free		Used	Usage (%)
		RAM	0x20000000	2x20005000	20 KB	18,45 KB	1,55 KB	7,73%
		FLASH	0x08000000	0x08010000	64 KB	59,42 KB	4,58 KB	7,15%
          ```
      * **Debug**:
        * **Edit**
          ```
          C:\ST\STM32CubeIDE_1.7.0\STM32CubeIDE\plugins\com.st.stm32cube.ide.mcu.debug.openocd_2.0.0.202106290712\resources\openocd\st_scripts\target\stm32f1x.cfg
          ```
          * => Realizar las siguientes modificaciones:
          ```Makefile
          #jtag scan chain
          if { [info exists CPUTAPID] } {
              set _CPUTAPID $CPUTAPID
          } else {
              if { [using_jtag] } {
                  # See STM Document RM0008 Section 26.6.3
                  set _CPUTAPID 0x3ba00477
              } {
                  # this is the SW-DP tap id not the jtag tap id
                  # => cambiar chipid de 0x1ba01477 a 0x2ba01477
                  set _CPUTAPID 0x2ba01477
              }
          }
          # => agregar la siguiente linea
          reset_config trst_only
          ```
	* **tp0_01_hw-sw-test** => **Debug As** => **1 STM32 C/C++ Application** => **Debugger** =>
	  **Debug probe** => **ST-LINK (OpenOCD)** => **Apply** => **OK**
          * Confirm Perspective Switch => **Switch**
          * **Step Over (F6)** / **Resume (F8)** / **Suspend**
          * **...**
        * **tp0_01_hw-sw-test** => **Terminate and Remove** => **Yes**

* **GitHub**
  * **Repositories** => **New** =>
    * Repository name: **tdse-tp0_01-hw_sw_test**
    * Description: **FIUBA - Electrónica - Taller de Sistemas Embebidos - Trabajo Práctico N°: 0 - Proyecto N°: 01**
    * => **Create repository**

* **Git Bash**
  ```
  git init
  git branch -M main
  git remote add origin https://github.com/Username/tdse-tp0_01-hw_sw_test.git

  git status
  git add --all
  git commit -m "first commit"
  git push -u origin main
  ```
</details>

---
### Works OK 
| Board               | STM32CubeIDE-Win | STM32CubeIDE-DEB |
| ------------------- | ---------------- | ---------------- |
| NUCLEO-F103RB       | OK - GS          |                  |              
| Blue Pill Original  | OK - JMC         |                  |
| Blue Pill Clone     | OK - JMC         | OK - PIM         |
