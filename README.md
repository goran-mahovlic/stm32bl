# Micropython version stm32flasher.py
import stm32flasher
stm32bl = stm32flasher.Stm32flasher(1, 115200,5)
stm32bl.write_file(0x8000000,"firmware.bin")

# STM32BL
STM32 MCU serial firmware loader.

## requirements
- python - tested only with python3.x
- py-serial - python library for serial port handling

## supported MCUs
Probably all STM32xxxx
please report any problems

## Examples:
- test connection
  `stm32loader -p /dev/tty.SLAB_USBtoUART`

- dump content of FLASH memory
  `stm32loader -p /dev/tty.SLAB_USBtoUART -d`

- save content of FLASH memory
  `stm32loader -p /dev/tty.SLAB_USBtoUART -r file.bin`

- write bin file to FLASH from selected address
  `stm32loader -p /dev/tty.SLAB_USBtoUART -a 0x08003000 -w file.bin`

- mass erase, write bin file to FLASH, verify and execute application
  `stm32loader -p /dev/tty.SLAB_USBtoUART -m -w file.bin -f -x`

- help
  `stm32loader -h`
