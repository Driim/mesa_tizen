include Makefile.sources

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = main/mesa-gbm.pc

AM_CFLAGS = \
	-I$(top_srcdir)/include \
	-I$(top_srcdir)/src \
	-I$(top_srcdir)/src/loader \
	-I$(top_srcdir)/src/gbm/main \
	$(DLOPEN_CFLAGS) \
	$(DEFINES) \
	$(VISIBILITY_CFLAGS)

lib_LTLIBRARIES = libmesagbm.la
include_HEADERS = main/gbm.h

libmesagbm_la_SOURCES = \
	$(gbm_core_FILES)

libmesagbm_la_LDFLAGS = \
	-no-undefined \
	-version-info 1:0 \
	$(GC_SECTIONS) \
	$(LD_NO_UNDEFINED)

libmesagbm_la_LIBADD = \
	$(top_builddir)/src/loader/libloader.la \
	$(top_builddir)/src/util/libmesautil.la \
	$(top_builddir)/src/util/libxmlconfig.la \
	$(DLOPEN_LIBS)

if HAVE_PLATFORM_WAYLAND
AM_CFLAGS += \
	$(WAYLAND_SERVER_CFLAGS) \
	-I$(top_srcdir)/src/egl/wayland/wayland-drm/
libmesagbm_la_LIBADD += $(WAYLAND_SERVER_LIBS)
endif

if HAVE_DRI2
libmesagbm_la_SOURCES += \
	$(gbm_dri_FILES)

AM_CFLAGS += \
	-DDEFAULT_DRIVER_DIR='"$(DRI_DRIVER_SEARCH_DIR)"' \
	$(LIBDRM_CFLAGS) \
	$(PTHREADSTUBS_CFLAGS)

libmesagbm_la_LIBADD += \
	$(LIBDRM_LIBS) \
	$(PTHREADSTUBS_LIBS)
endif

TESTS = gbm-symbols-check
EXTRA_DIST = gbm-symbols-check meson.build

include $(top_srcdir)/install-lib-links.mk
