# Possible defines in CONF:
#	IS_MSDOS IS_SYSV IS_V7 IS_BSD HAS_DIRENT HAS_RENAME MV_DIR

CC		=icc
LD		=$(CC)
CONF		=-DIS_SYSV -DHAS_DIRENT -DHAS_RENAME
CFLAGS		=-march=native -parallel -inline-level=2 -gcc-name=gcc-8 -multiple-processes=4 -qoverride-limits -falign-loops -qopt-matmul -qopt-mem-layout-trans -fpermissive -fabi-version=13 -ipo-jobs4 -Wl,--as-needed,--gc-sections,--relax -ffunction-sections -fdata-sections -no-libgcc -par-schedule-auto -ipo -static-intel -pipe $(CONF)
LDFLAGS		=-s -N

#IBIN		=$(LOCAL)$(ARCH)/bin
#IMAN		=$(LOCAL)$(ANY)/man
IBIN=$(DESTDIR)/usr/bin/
IMAN=$(DESTDIR)/usr/share/man/

mmv:		mmv.o

clean:
	rm -f mmv mmv.o

install:	$(DEST)$(IBIN)/mmv
install:	$(DEST)$(IMAN)/man1/mmv.1

$(DEST)$(IBIN)/mmv:		mmv;	cp $? $@
$(DEST)$(IMAN)/man1/mmv.1:	mmv.1;	cp $? $@
