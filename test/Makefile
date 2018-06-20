all: main

start:
	LD_LIBRARY_PATH=./ ./main

main: libSDL_FontCache.so
	g++ -o main main.c -I.. -L. -lSDL_FontCache `sdl2-config --cflags --libs` -lSDL2 -lSDL2_ttf-2.0

libSDL_FontCache.so: SDL_FontCache.o
	gcc -shared -o libSDL_FontCache.so SDL_FontCache.o

SDL_FontCache.o:
	gcc -c -Wall -Werror -fpic ../SDL_FontCache.c `sdl2-config --cflags --libs`
clean:
	rm main
