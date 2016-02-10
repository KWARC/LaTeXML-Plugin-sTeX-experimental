STEXDIR = ../..
ETCSTYDIR =  $(STEXDIR)/sTeX/sty/etc
HTMLSTYDIR = ../lib/LaTeXML/resources/Package
XSLTSTY = $(STEXDIR)/sTeX/xsl/htmlpost.xsl
TARGET = test

all: $(TARGET).xml $(TARGET).xhtml

$(TARGET).xml: $(TARGET).tex
	latexmlc --preamble pre.tex --postamble post.tex \
	-path $(ETCSTYDIR) -path $(HTMLSTYDIR) $< > $@

$(TARGET).xhtml: $(TARGET).xml  $(TARGET).tex
	xsltproc $(XSLTSTY) $< > $@
