SOURCES=presentation.md template/*

all: pdf html

present: 
	bs serve

present-impressive:
	# sudo apt install impressive
	@echo "Use mouse to highlight things"
	@echo "Return to spotlight, mouse wheel controls spotlight size"
	@echo "Tab for overview screen"
	@echo "Z for zoom in/out"
	@echo "Drag with right mouse button in zoom, just don't be too quick!"
	@echo "F toggles full-screen"
	@echo "Ctrl to navigate without transitions"
	@echo 'Use [ ] and { } keys to adjust gamma and black levels, 7 and 8 for highlight adjustment'
	impressive --darkness 50 -q -T 500 -t Crossfade,FadeOutFadeIn,PagePeel,SlideDown,SlideLeft,SlideRight,SlideUp,SqueezeDown,SqueezeLeft,SqueezeRight,SqueezeUp,WipeBlobs,WipeBrightness1,WipeBrightness2,WipeCenterIn,WipeCenterOut,WipeClouds,WipeDown,WipeDownLeft,WipeDownRight,WipeLeft,WipeRight,WipeUp,WipeUpLeft,WipeUpRight slides.pdf

install-modules:
	npm install -g backslide

pdf: $(SOURCES)
	bs pdf
	ln -sf pdf/presentation.pdf ./slides.pdf
	# for backwards compatibility with old links
	ln -sf pdf/presentation.pdf ./slidecontent.pdf

html: $(SOURCES)
	bs export
	ln -sf dist/presentation.html ./index.html

output: 
	@echo $(SOURCES)
