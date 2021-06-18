TARGET = boot_sect_hello.bin

all: $(TARGET)

$(TARGET): boot_sect_hello.asm
	nasm -f bin $< -o $@

.PHONY: qemu
qemu: $(TARGET)
	@echo "Press Ctrl-A and then X to exit QEMU"
	@echo
	@qemu-system-x86_64 -nographic $(TARGET)

.PHONY: xxd
xxd: $(TARGET)
	@echo "Examine the binary data..."
	@echo
	@xxd $(TARGET)

.PHONY: clean
clean:
	-rm -f $(TARGET)
