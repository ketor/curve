.PHONY: download build install clean

all: clean download build install

prefix?= "$(PWD)"
from_source?= 0

build:
	@cd rocksdb && USE_RTTI=1 PORTABLE=1 make static_lib -j$(nproc)

install:
	@cd rocksdb && make install PREFIX=$(prefix)

clean:
	@rm -rf include lib

download:
	# @git clone -b 6.28.fb https://github.com/facebook/rocksdb
	@git submodule update --init rocksdb
