# REQUIREMENTS
#   latex
#   pandoc

TARGET=HW2
TEMPLATE=default.latex

OPTIONS+=-V geometry:margin=1in


all: pandoc render open cleantemps cleanlogs
verbose: pandoc render open openlog cleantemps
clean: cleantemps cleanlogs cleanoutput
run: all


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
	open $(TARGET).pdf

openlog: $(TARGET).log
	open $(TARGET).log

cleantemps:
	rm -rf *.aux *.out

cleanlogs:
	rm -rf *.log

cleanoutput:
	rm -rf *.pdf *.tex

	
