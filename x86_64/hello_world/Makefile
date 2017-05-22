BINARY = program.x
SRC_DIR = src
BUILD_DIR = build

AS=nasm
ASFLAGS = -f elf64

LD=ld
LDLIBS = # specific libraries; -lhdf5 
LDFLAGS = # paths to libraries; -L/path/to/library


.PHONY: all
.DEFAULT: all
all: $(BUILD_DIR)/$(BINARY)

$(BUILD_DIR)/%.o: $(SRC_DIR)/%.asm | $(BUILD_DIR)
	$(AS) $(ASFLAGS) $^ -o $@

$(BUILD_DIR)/$(BINARY): $(BUILD_DIR)/hello.o
	$(LD) $(LDFLAGS) $< $(LDLIBS) -o $@

$(BUILD_DIR): 
	mkdir -p $@

.PHONY: clean
clean:
	rm -rf $(BUILD_DIR)
