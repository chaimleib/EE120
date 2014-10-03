# REQUIREMENTS
#   latex   (use MacTeX, MikTeX, etc)
#   pandoc	(use brew to install on Mac, Windows download from
#   	https://github.com/jgm/pandoc/releases
#   	)

TARGET=$(shell basename `pwd`)
TEMPLATE=default.latex

HWNUM=$(shell basename `pwd` | grep -o '[0-9]\+')

OPTIONS=-V geometry:margin=1in -V hwnum:$(HWNUM)


all: pandoc render open cleantemps cleanlogs
verbose: pandoc render open openlog cleantemps
clean: cleantemps cleanlogs cleanoutput
run: all


PLATFORM=$(shell ([[ -n "$(OSTYPE)" ]] && echo $(OSTYPE) || echo $(OS) ) | grep -o '[^0-9\-]\+')
ifeq ($(PLATFORM), Windows_NT)
	PLATFORM=cygwin
endif
ifeq ($(PLATFORM), cygwin)
	OPEN=cygstart
else
	OPEN=open
endif
	

pandoc: $(TARGET).md
	pandoc \
		--latex-engine=xelatex \
		$(OPTIONS) \
		--template=$(TEMPLATE) \
		--from markdown \
		--to latex \
		$(TARGET).md \
		-o $(TARGET).tex


render: $(TARGET).tex
	pdflatex $(TARGET).tex
	#pandoc \
	#	--latex-engine=xelatex \
	#	--from latex \
	#	--to latex \
	#	$(TARGET).tex \
	#	-o $(TARGET).pdf

open: $(TARGET).pdf
	$(OPEN) $(TARGET).pdf

openlog: $(TARGET).log
	$(OPEN) $(TARGET).log

cleantemps:
	rm -rf *.aux *.out

cleanlogs:
	rm -rf *.log

cleanoutput:
	rm -rf *.pdf *.tex

	
