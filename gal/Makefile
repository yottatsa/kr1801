sources = cpu.pld

all: $(sources:.pld=.jed)
	@ls -lh $^

GALasm/src:
	git submodule update --init GALasm

GALasm/src/galasm: GALasm/src
	make -C GALasm/src galasm

%.jed:	%.pld GALasm/src/galasm Makefile
	GALasm/src/galasm -v $<

clean:
	rm -f $(sources:.pld=.jed)

.PHONY: all clean
