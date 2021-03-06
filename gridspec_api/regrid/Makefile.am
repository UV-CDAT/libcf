#
# $Id: Makefile.am 915 2012-01-09 16:58:08Z pletzer $
#

AM_CPPFLAGS = -I@NETCDFDIR@/include -I$(top_srcdir)/src			\
-I$(top_srcdir)/include -I$(srcdir)/../global -I$(srcdir)/../coord	\
-I$(srcdir)/../grid -I$(srcdir)/../data

include_HEADERS = nccf_regrid.h

noinst_LTLIBRARIES = libnccf_regrid.la
libnccf_regrid_la_SOURCES = nccf_def_regrid.c				\
nccf_def_regrid_from_file.c nccf_put_regrid.c nccf_free_regrid.c	\
nccf_apply_regrid.c nccf_apply_regrid_type.h				\
nccf_inq_regrid_ntargets.c nccf_inq_regrid_nvalid.c			\
nccf_inq_regrid_nnodes.c nccf_add_regrid_forbidden.c			\
nccf_compute_regrid_weights.c nccf_inq_regrid_weights.c                 \
nccf_get_regrid_weights_pointer.c

INTLIBS = libnccf_regrid.la ../data/libnccf_data.la	\
../grid/libnccf_grid.la ../global/libnccf_global.la	\
../coord/libnccf_coord.la ../../src/libcf_src.la

EXTLIBS = -lnetcdf 

noinst_PROGRAMS = tst_cubesphere_to_lonlat_regrid \
tst_tripolar_to_lonlat_regrid_from_weights

check_PROGRAMS = \
  tst_lonlat_regrid \
  tst_slanted_lonlat_regrid \
  tst_lonlat_to_lonlat_regrid \
  tst_tripolar_to_lonlat_regrid	\
  tst_put_and_def_from_file \
  tst_mask tst_mask2 \
  tst_periodic tst_periodic2 tst_periodic3

tst_lonlat_regrid_SOURCES = tst_lonlat_regrid.c
tst_lonlat_regrid_LDADD = $(INTLIBS) $(EXTLIBS)

tst_slanted_lonlat_regrid_SOURCES = tst_slanted_lonlat_regrid.c
tst_slanted_lonlat_regrid_LDADD = $(INTLIBS) $(EXTLIBS)

tst_lonlat_to_lonlat_regrid_SOURCES = tst_lonlat_to_lonlat_regrid.c
tst_lonlat_to_lonlat_regrid_LDADD = $(INTLIBS) $(EXTLIBS)

tst_tripolar_to_lonlat_regrid_SOURCES = tst_tripolar_to_lonlat_regrid.c
tst_tripolar_to_lonlat_regrid_LDADD = $(INTLIBS) $(EXTLIBS)

tst_put_and_def_from_file_SOURCES = tst_put_and_def_from_file.c
tst_put_and_def_from_file_LDADD = $(INTLIBS) $(EXTLIBS)

tst_cubesphere_to_lonlat_regrid_SOURCES = tst_cubesphere_to_lonlat_regrid.c
tst_cubesphere_to_lonlat_regrid_LDADD = $(INTLIBS) $(EXTLIBS)

tst_tripolar_to_lonlat_regrid_from_weights_SOURCES = tst_tripolar_to_lonlat_regrid_from_weights.c
tst_tripolar_to_lonlat_regrid_from_weights_LDADD = $(INTLIBS) $(EXTLIBS)

tst_mask_SOURCES = tst_mask.c
tst_mask_LDADD = $(INTLIBS) $(EXTLIBS)

tst_mask2_SOURCES = tst_mask2.c
tst_mask2_LDADD = $(INTLIBS) $(EXTLIBS)

tst_periodic_SOURCES = tst_periodic.c
tst_periodic_LDADD = $(INTLIBS) $(EXTLIBS)

tst_periodic2_SOURCES = tst_periodic2.c
tst_periodic2_LDADD = $(INTLIBS) $(EXTLIBS)

tst_periodic3_SOURCES = tst_periodic3.c
tst_periodic3_LDADD = $(INTLIBS) $(EXTLIBS)

TESTS = $(check_PROGRAMS)

# files generated by tests
CLEANFILES = *.nc
