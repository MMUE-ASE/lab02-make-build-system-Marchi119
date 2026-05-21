# Exercise 3 — Two files and a pattern rule
# Concepts: substitution reference, static pattern rule, refactoring explicit rules
#
# This exercise has two parts:
#   Part A — start with two explicit rules (like Exercise 2, repeated twice)
#   Part B — replace them with a single pattern rule
# -----------------------------------------------------------------------

CC       = arm-none-eabi-gcc
CFLAGS   = -mcpu=cortex-m4 -mthumb -mfloat-abi=soft -O0 -ffreestanding
BUILDDIR = output

# TODO A1: List the two source files in SRCS.
SRCS = utils.c math.c

# TODO B1: Derive OBJS from SRCS using a substitution reference.
OBJS = $(SRCS:%.c=$(BUILDDIR)/%.o)

# TODO B2.3: Update "all" to depend on $(OBJS)
all: $(OBJS)

$(BUILDDIR):
	mkdir -p $@

# TODO B2.2: Write the pattern rule below (Reemplaza a A3 y A4)
$(OBJS): $(BUILDDIR)/%.o : %.c | $(BUILDDIR)
	$(CC) $(CFLAGS) -c $< -o $@

.PHONY: all clean

clean:
	rm -rf $(BUILDDIR)
