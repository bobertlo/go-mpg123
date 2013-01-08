mpg123-go: libmpg123 bindings for go
====================================

mpg123-go is a library that provides bindings to libmpg123.

Not all library functions are present, but there are enough bindings to
decode an MP3 file using mpg123_open and mpg123_read. However, decoding
from a file reader and feeding data directly to the decoder are not yet
supported.

This library is still very much a work in progress.

Usage
-----

	decoder, err := mpg123.NewMpg123("")
	if err != nil {
		panic("error initializing mpg123 decoder")
	}
	err = decoder.Open("test.mp3")
	if err != nil {
		panic("error opening mp3 file")
	}
	defer decoder.Close()
	buf := make([]byte, 1024)
	len, err := decoder.Read(buf)
	if err != nil && err != mpg123.EOF {
		panic("error decoding mp3")
	}

