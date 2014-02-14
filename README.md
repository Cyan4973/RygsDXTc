# Real-Time DXT1/DXT5 C compression library #

Based on Fabian Giesen ("ryg")'s work.
Original Homepage :  [http://farbrausch.com/~fg/code/index.html](http://farbrausch.com/~fg/code/index.html).

This version is a faster variant, tested on x86 CPU.
It is designed as a drop-in replacement of the original one. Therefore, interface is unchanged. 


## Functions ##

* rygCompress() — compress a texture, to DXT1 or DXT5 format; source must be provided in 32-bits RGBA format


### rygCompress() ###

#### Description ####

void rygCompress( unsigned char *dst, unsigned char *src, int w, int h, int isDxt5 );

#### Parameters ####

* unsigned char *dst

  Pointer to the Destination memory buffer.
  The buffer must already be allocated.
  The required size of the buffer is :
  for DXT1 : dstSize = srcSize / 8
  for DXT5 : dstSize = srcSize / 4 

* unsigned char *src

  Pointer to the Source memory buffer,
  which contains the texture to compress.
  The source texture format must be 32 bits RGBA.
  Source memory buffer size is implicit, and must be :
  srcSize = w * h * 4

* int w

  Width of source texture, in pixels
  
* int h

  Height of source texture, in pixels
  
* int isDxt5

  0 : will be compressed into DXT1 format
  1+: will be compressed into DXT5 format
  