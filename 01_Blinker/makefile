CHAIN=arm-none-eabi


all: start.s main.c
	$(CHAIN)-as start.s -o start.o
	$(CHAIN)-gcc -c main.c -o main.o
	$(CHAIN)-ld start.o main.o -T memmap.ld -o main.elf
	$(CHAIN)-objcopy main.elf spl.boot -O binary
	../bin/mk-gpimage 0x402f0400 spl.boot MLO
copy:
	cp spl.boot ../boot

clean:
	rm -rf *.o
	rm -rf *.elf
	rm -rf *.boot
	rm -rf ../boot/*.boot
	rm MLO
