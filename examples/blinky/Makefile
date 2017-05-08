CC = xtensa-lx106-elf-gcc
CFLAGS = -I. -I /mnt/d/PAPPS/esp8266/esp-open-sdk/xtensa-lx106-elf/xtensa-lx106-elf/include -I /mnt/d/PAPPS/esp8266/esp-open-sdk/sdk/include -mlongcalls
LDLIBS = -nostdlib -Wl,--start-group -lmain -lnet80211 -lwpa -llwip -lpp -lphy -lc -Wl,--end-group -lgcc
LDFLAGS = -L /mnt/d/PAPPS/esp8266/esp-open-sdk/sdk/lib -L /mnt/d/PAPPS/esp8266/esp-open-sdk/sdk/ld -Teagle.app.v6.ld

blinky-0x00000.bin: blinky
	esptool.py elf2image $^

blinky: blinky.o

blinky.o: blinky.c

flash: blinky-0x00000.bin
#	esptool.py --chip esp8266 --port com3 --baud 150000 write_flash 0 blinky-0x00000.bin 0x10000 blinky-0x10000.bin
	cmd.exe /c "py D:\PAPPS\esp8266\esp-open-sdk\xtensa-lx106-elf\bin\esptool.py --chip esp8266 --port com3 --baud 1500000 write_flash 0 blinky-0x00000.bin 0x10000 blinky-0x10000.bin"

clean:
	rm -f blinky blinky.o blinky-0x00000.bin blinky-0x10000.bin
