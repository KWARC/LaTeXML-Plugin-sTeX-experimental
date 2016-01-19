RNC =  $(shell ls *.rnc)
RNG =  $(RNC:%.rnc=%.rng)
MOD =  ltxml+omdoc.model

all: $(MOD)

ltxml+omdoc.model: %.model: $(RNG) compileSchema-ltxml+omdoc.pl
	perl compileSchema-ltxml+omdoc.pl


$(RNG): %.rng: %.rnc $(OMDOC.rnc) $(LATEXML.rnc)
		trang -I rnc -O rng $< $@
clean:		
		rm -f *~ 
distclean:	clean
		rm -f *.rng
