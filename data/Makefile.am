SUBDIRS = icons

desktopdir 	 = $(datadir)/applications
desktop_in_files = gitg.desktop.in
desktop_DATA 	 = $(desktop_in_files:.desktop.in=.desktop)
@INTLTOOL_DESKTOP_RULE@

schemasdir	 = $(GCONF_SCHEMA_FILE_DIR)
schemas_in_files = gitg.schemas.in
schemas_DATA 	 = $(schemas_in_files:.schemas.in=.schemas)
@INTLTOOL_SCHEMAS_RULE@

man_MANS = gitg.1

gitglangsdir = $(datadir)/gitg/language-specs
gitglangs_DATA = gitgdiff.lang

gitgstylesdir = $(datadir)/gitg/styles
gitgstyles_DATA = gitgstyle.xml

if GCONF_SCHEMAS_INSTALL
install-data-local:
	        if test -z "$(DESTDIR)" ; then \
	                for p in $(schemas_DATA) ; do \
	                        GCONF_CONFIG_SOURCE=$(GCONF_SCHEMA_CONFIG_SOURCE) $(GCONFTOOL) --makefile-install-rule $(top_builddir)/data/$$p ; \
	                done \
	        fi
else
install-data-local:
endif

EXTRA_DIST = 				\
	$(desktop_in_files)		\
	$(schemas_in_files)		\
	$(gitglangs_DATA)		\
	$(gitgstyles_DATA)		\
	$(man_MANS)

CLEANFILES =	 			\
	$(desktop_DATA)			\
	$(schemas_DATA)


-include $(top_srcdir)/git.mk
