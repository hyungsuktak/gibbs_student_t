LATEX       = pdflatex
BIBTEX      = bibtex
BASH        = bash -c
ECHO        = echo
RM          = rm -rf
RM_TMP      = ${RM} $(foreach suff, ${TMP_SUFFS}, ${NAME}.${suff})

TMP_SUFFS   = pdf aux bbl blg log dvi ps eps out brf synctex.gz
SUFF        = pdf

NAME    = ms
DOC_OUT = ${NAME}.${SUFF}

default: ${DOC_OUT}

${NAME}.pdf: ${NAME}.bbl ${NAME}.tex
	${LATEX} ${NAME}.tex -draftmode
	${LATEX} ${NAME}.tex 

${NAME}.bbl: ${NAME}.aux
	${BIBTEX} ${NAME}.aux 

${NAME}.aux: ${NAME}.bib
	${LATEX} ${NAME}.tex -draftmode
	${LATEX} ${NAME}.tex -draftmode

clean:
	${RM_TMP}
	${RM}  msNotes.bib
