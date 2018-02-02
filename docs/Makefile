all: pdf html

present: 
	bs serve

present-impressive:
	# sudo apt install impressive
	@echo "Use mouse to highlight things"
	@echo "Return to spotlight, mouse wheel controls spotlight size"
	@echo "Tab for overview screen"
	@echo "Z for zoom in/out"
	@echo "F toggles full-screen"
	@echo "Ctrl to navigate without transitions"
	@echo 'Use [ ] and { } keys to adjust gamma and black levels, 7 and 8 for highlight adjustment'
	impressive slides.pdf

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

