include $(top_builddir)/version.mk

# Help the Developers and yourself.  Just use the C locale and settings
# for the compilation. They can still be overriden by make LANG=<whatever>
# but that is general a not very good idea
LANG=C
LC_ALL=C

BUILT_SOURCES =
BUILT_MANS =
EXTRA_DIST = $(BUILT_SOURCES)
EXTRA_DIST += $(man1_MANS)
SUFFIXES =

man1_MANS =
man1_MANS += $(built_men)

built_men =
built_men += clitoris.man
built_men += hxdiff.man
built_men += shack.man

BUILT_SOURCES += $(built_men)
EXTRA_DIST += author.h2m

VPATH += @top_srcdir@/src
SUFFIXES += .yuck
SUFFIXES += .man
.yuck.man:
	$(AM_V_GEN) PATH="$(top_builddir)/build-aux:$${PATH}" \
		yuck$(EXEEXT) genman \
			--package "$(PACKAGE_NAME)" \
			-i "$(srcdir)/author.h2m" \
			-o $@ --version-file "$(top_builddir)/.version" $<

## Makefile.am ends here
