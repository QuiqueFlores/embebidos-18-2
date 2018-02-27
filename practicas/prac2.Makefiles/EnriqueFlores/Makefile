#Archivo MakeFile con Objetvivos falsos y variables

PROYECTO=muestreo
DESTDIR=/usr/local/bin
CFLAGS=-Wall
LDFLAGS=-lm
CC=gcc 

all: $(PROYECTO)

%.o: %.c 					# objetivo : dependencia 
	$(CC) -c $< $(CFLAGS)	# $< Nombre de la primer dependencia 

objects := $(patsubst %.c,%.o,$(wildcard *.c))
$(PROYECTO): $(objects)
	$(CC) $^ -o $@ $(LDFLAGS)

.PHONY: clean

install: all
	if [ ! -d $(DESTDIR) ]; then \
		sudo mkdir $(DESTDIR); \
	fi; \
	sudo cp $(PROYECTO) $(DESTDIR)

unistall:
	sudo rm $(DESTDIR)/$(PROYECTO)

clean:
	rm -f *o $(PROYECTO)