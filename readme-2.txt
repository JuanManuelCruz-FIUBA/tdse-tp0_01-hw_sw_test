FIUBA - Electrónica - Taller de Sistemas Embebidos
Trabajo Práctico N°: 0 - Proyecto N°: 01

Board:		NUCLEO-F103RB
IDe:		STM32CubeIDE Version: 1.7.0

Conectar NUCLEO-F103RB a la PC
Ejecutar STM32CubeIDE

File (Alt+Shift+N) => New => STM32 Project
	BOARD Selector Commercial Part Number: NUCLEO-F103RB => Select => Next
	Project Name:	tdse-tp0_01-hw_sw_test => Next => Finish
	Board Project Options: 
		Initialize all peripherals with their default Mode ? => Yes

Project Explorer:
	tp0_1_hw-sw-test => Core => Src => main.c => 
						Copy and paste the following code on line # 102:
	
	HAL_GPIO_TogglePin(LD2_GPIO_Port, LD2_Pin);
	HAL_Delay(500);

	Save(Ctrl+S) => tp0_1_hw-sw-test => Build Project
	Console:
		arm-none-eabi-size   tp0_1_hw-sw-test.elf 
			text	   data	    bss	    dec	    hex	filename
			5676	     20	   1636	   7332	   1ca4	tp0_1_hw-sw-test.elf
		Finished building: default.size.stdout
	
		Finished building: tdse-tp0_01-hw_sw_test.bin

		Finished building: tdse-tp0_01-hw_sw_test.list
	
		hh:mm:ss Build Finished. 0 errors, 0 warnings. (took Xs.YYYms)

	Bulid Analyzer:
		Memory Regions:
		Region	Start addr	End addr	Size	Free		Used	Usage (%)
		RAM		0x20000000	2x20005000	20 KB	18,39 KB	1,61 KB	8,05%
		FLASH	0x08000000	0x08010000	128 KB	122,44 KB	5,56 KB	4,35%

	Debug:
		tp0_1_hw-sw-test => Debug As => 1 STM32 C/C++ Application => Debugger =>
							Debug probe => ST-LINK (ST-LINK GDB server) => Apply => OK
							Confirm Perspective Switch => Switch
							Step Over (F6) / Resume (F8) / Suspend
							...
		tp0_1_hw-sw-test => Terminate and Remove => Yes

GitHub => Repositories =>
			New =>	Repository name: tdse-tp0_01-hw_sw_test
					Description: FIUBA - Electrónica - Taller de Sistemas 
					Embebidos - Trabajo Práctico N°: 0 - Proyecto N°: 01
				=>	Create repository

Git Bash =>

git init
git branch -M main
git remote add origin https://github.com/JuanManuelCruz-FIUBA/tdse-tp0_01-hw_sw_test.git

git status
echo "# FIUBA - Electrónica - Taller de Sistemas Embebidos - Trabajo Práctico N°: 0 - Proyecto N°: 01" >> README.md
git add --all 
git commit -m "first commit"
git push -u origin main
