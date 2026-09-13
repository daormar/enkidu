bin_SCRIPTS=

libexec_SCRIPTS=

mypkglibdir = $(libdir)/@PACKAGE@
mypkglib_DATA =

CLEANFILES = $(bin_SCRIPTS) $(libexec_SCRIPTS) $(mypkglib_DATA)

EXTRA_DIST =

# Build using suffix rules (portable)
SUFFIXES= .sh .py .r .R

.sh :
	rm -f $@
	echo "#! " $(BASH) > $@
	echo "enkidu_pkgname=\"$(PACKAGE_NAME)\"" >> $@
	echo "enkidu_version=\"$(PACKAGE_VERSION)\"" >> $@
	echo "enkidu_bindir=\"$(bindir)\"" >> $@
	echo "enkidu_libexecdir=\"$(libexecdir)\"" >> $@
	echo "enkidu_datadir=\"$(datadir)/$(PACKAGE_NAME)\"" >> $@
	echo "enkidu_pkglibdir=\"$(libdir)/$(PACKAGE_NAME)\"" >> $@
	echo "enkidu_debasher_programs_dir=\"$(datadir)/$(PACKAGE_NAME)/debasher_programs\"" >> $@
	echo "BASH=\"$(BASH)\"" >> $@
	echo "PYTHON=\"$(PYTHON)\"" >> $@
	echo "DEBASHER_HOME_DIR=\"$(DEBASHER_HOME_DIR)\"" >> $@
	cat $< >> $@
	chmod ugo+x $@

.py:
	rm -f $@
	echo "#! " $(PYTHON) > $@
	cat $< >> $@
	chmod ugo+x $@

.r:
	rm -f $@
	echo "#! " $(RSCRIPT) > $@
	cat $< >> $@
	chmod ugo+x $@

.R:
	rm -f $@
	echo "#! " $(RSCRIPT) > $@
	cat $< >> $@
	chmod ugo+x $@
