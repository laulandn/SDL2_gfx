# Makefile to build the SDL2_gfx tests

srcdir  = .

CC      = gcc
EXE	= 
CFLAGS  = -g -O2 -D_THREAD_SAFE -I/usr/local/include -I/usr/local/include/SDL2 -I/usr/X11R6/include -I/usr/X11R6/include -DHAVE_OPENGL -g
LIBS	=  -lSDL2_test -L/usr/local/lib -lSDL2 -lSDL2_gfx 

TARGETS = \
	testgfx$(EXE) \
	testrotozoom$(EXE) \
	testimagefilter$(EXE) \
	testframerate$(EXE) \

all: Makefile $(TARGETS)

Makefile: $(srcdir)/Makefile.in
	$(SHELL) config.status $@

testgfx$(EXE): $(srcdir)/testgfx.c
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS) 

testrotozoom$(EXE): $(srcdir)/testrotozoom.c
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS) 

testimagefilter$(EXE): $(srcdir)/testimagefilter.c
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS) 

testframerate$(EXE): $(srcdir)/testframerate.c
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS) 

clean:
	rm -f $(TARGETS)
	rm -f *~
	rm -f *.user
	rm -f *.stackdump

distclean: clean
	rm -f Makefile
	rm -f config.status config.cache config.log
	rm -rf $(srcdir)/autom4te*
	rm -rf TestGfx TestRotozoom TestImageFilter TestFramerate Win32
	
