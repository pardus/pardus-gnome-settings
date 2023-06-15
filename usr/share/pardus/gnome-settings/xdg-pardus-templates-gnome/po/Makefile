#!/usr/bin/make -f

POTFILES := $(shell cat files)

all: generate-locales

generate-pot: files
	intltool-update --pot --gettext-package=xdg-pardus-templates-gnome

generate-locales:
	for i in $$(find $$1 -name "*.po"); do \
		code=$$(echo $$i | sed 's/.po//'); \
		mkdir -p locale/$$code/LC_MESSAGES/; \
	msgfmt -o locale/$$code/LC_MESSAGES/xdg-pardus-templates-gnome.mo $$i; \
	done; \
	cp -R locale/* ../../../../locale

update-po:
	for i in *.po; do \
		code=$$(echo $$i | sed 's/.po//'); \
		intltool-update --gettext-package=xdg-pardus-templates-gnome --dist $$code; \
	done

# vim:ts=4
