
SHELL = /bin/sh

.SUFFIXES:

.PHONY: install clean

ifeq ($(bindir),)
  $(error bindir is not set)
endif

version ?= 1.22.10

install: yarn-v$(version)
	@ln -nvfrst $(bindir) $(wildcard $</bin/*)

#yarn-%.js: url = https://github.com/yarnpkg/yarn/releases/download/v$(*)/yarn-v$(*).js
#yarn-%.js:
#	curl -sSfJL -z "$@" -o $@ $(url)

clean:
	find -mindepth 1 -maxdepth 1 -type d | xargs -r rm -rf

yarn-v%.tar.gz: url = https://github.com/yarnpkg/yarn/releases/download/v$(*)/yarn-v$(*).tar.gz
yarn-v%.tar.gz:
	curl -sSfJL -z "$@" -o $@ $(url)
	@touch $@

yarn-v%: yarn-v%.tar.gz
	tar xmf $<
