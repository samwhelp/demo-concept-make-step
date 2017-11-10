
default: demo

demo:
	gcc main.c -o demo

install:
	install demo /usr/local/bin

uninstall:
	rm /usr/local/bin/demo

clean:
	rm ./demo -f
	rm ./msg.h -f

help:
	@echo 'Usage: make [command]'
	@echo 'Help: make help'
	@echo
	@echo 'Ex:'
	@echo 'make'
	@echo 'make install'
	@echo 'make clean'
	@echo 'make uninstall'

.PHONY: default install uninstall clean help
