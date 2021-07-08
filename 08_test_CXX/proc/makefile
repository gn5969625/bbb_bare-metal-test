OBJ=obj/
PARENTOBJ=../obj/

all: dir  $(OBJ)proc_init.o $(OBJ)UART.o $(OBJ)GPIO.o $(OBJ)control_module.o $(OBJ)clock_module.o $(OBJ)pad.o $(OBJ)proc_handlers.o
	$(CHAIN)ld -r $(OBJ)*.o -o $(PARENTOBJ)proc.o

dir:
	@mkdir -p $(OBJ)

$(OBJ)proc_init.o: proc_init.c
	$(CHAIN)gcc $(CFLAGS) -c proc_init.c -o $(OBJ)proc_init.o

$(OBJ)proc_handlers.o: proc_handlers.c
	$(CHAIN)gcc $(CFLAGS) -c proc_handlers.c -o $(OBJ)proc_handlers.o

$(OBJ)GPIO.o: GPIO.c
	$(CHAIN)gcc $(CFLAGS) -c GPIO.c -o $(OBJ)GPIO.o

$(OBJ)pad.o: pad.c
	$(CHAIN)gcc $(CFLAGS) -c pad.c -o $(OBJ)pad.o

$(OBJ)control_module.o: control_module.c
	$(CHAIN)gcc $(CFLAGS) -c control_module.c -o $(OBJ)control_module.o

$(OBJ)clock_module.o: clock_module.c
	$(CHAIN)gcc $(CFLAGS) -c clock_module.c -o $(OBJ)clock_module.o

$(OBJ)UART.o: UART.c
	$(CHAIN)gcc $(CFLAGS) -c UART.c -o $(OBJ)UART.o


clean:
	rm -rf $(OBJ)*.o
