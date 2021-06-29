TARGET = boot_sect_simple.bin

all: $(TARGET)

$(TARGET): boot_sect_simple.asm
	nasm -f bin $< -o $@

.PHONY: qemu
qemu: $(TARGET)
	@echo "Press Ctrl-A and then X to exit QEMU"
	@echo
	@qemu-system-x86_64 -nographic $(TARGET)

.PHONY: hexdump
hexdump: $(TARGET)
	@echo "check content in .bin file"
	@echo
	@hexdump -C $(TARGET)
.PHONY: clean
clean:
	-rm -f $(TARGET)
