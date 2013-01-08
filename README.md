mpg123-go
=========

Introduction
------------

mpg123-go is a library that provides bindings to libmpg123.

Not all library functions are present, but there are enough bindings to
decode an MP3 file using mpg123_open and mpg123_read. However, decoding
from a file reader and feeding data directly to the decoder are not yet
supported.

This library is still very much a work in progress.

Examples
--------

An example program is included in examples/rawdump. This program decodes
an MP3 file and writes the raw PCM data to a file.

	go get github.com/go-mpg123/examples/rawdump
	rawdump <file.mp3> <outfile.raw>

This raw audio file may be played using mplayer:

	mplayer -demuxer rawaudio -rawaudio rate=<samplerate>:channels=<channels> out.raw
