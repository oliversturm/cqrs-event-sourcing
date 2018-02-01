all: pdf html

present: 
	bs serve

install-modules:
	npm install -g backslide

pdf: presentation.md
	bs pdf
	cp pdf/presentation.pdf ./slides.pdf
	# for backwards compatibility with old links
	cp pdf/presentation.pdf ./slidecontent.pdf

html: presentation.md
	bs export
	cp dist/presentation.html ./index.html
	
