SHELL = /bin/sh

.SUFFIXES:

.PHONY: install clean

export bindir := $(abspath bin)
export PATH := $(bindir):$(PATH)

install:
	mkdir $(bindir) || find $(bindir) -type l -delete
	$(MAKE) -C node install
	$(MAKE) -C yarn install

clean:
	@find $(bindir) -type l -delete
	$(MAKE) -C yarn clean
	$(MAKE) -C node clean
