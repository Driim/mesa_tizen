# Copyright © 2012 Intel Corporation
#
# Permission is hereby granted, free of charge, to any person obtaining a
# copy of this software and associated documentation files (the "Software"),
# to deal in the Software without restriction, including without limitation
# the rights to use, copy, modify, merge, publish, distribute, sublicense,
# and/or sell copies of the Software, and to permit persons to whom the
# Software is furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice (including the next
# paragraph) shall be included in all copies or substantial portions of the
# Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL
# THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
# FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS
# IN THE SOFTWARE.

SUBDIRS = src

AM_DISTCHECK_CONFIGURE_FLAGS = \
	--enable-dri \
	--enable-dri3 \
	--enable-egl \
	--enable-gallium-tests \
	--enable-gallium-osmesa \
	--enable-llvm \
	--enable-gbm \
	--enable-gles1 \
	--enable-gles2 \
	--enable-glx \
	--enable-glx-tls \
	--enable-nine \
	--enable-opencl \
	--enable-opencl-icd \
	--enable-opengl \
	--enable-va \
	--enable-vdpau \
	--enable-xa \
	--enable-xvmc \
	--enable-llvm-shared-libs \
	--enable-libunwind \
	--with-platforms=x11,wayland,drm,surfaceless,tizen \
	--with-dri-drivers=i915,i965,nouveau,radeon,r200,swrast \
	--with-gallium-drivers=i915,nouveau,r300,pl111,r600,radeonsi,freedreno,svga,swrast,vc4,tegra,virgl,swr,etnaviv,imx \
	--with-vulkan-drivers=intel,radeon

ACLOCAL_AMFLAGS = -I m4

EXTRA_DIST = \
	autogen.sh \
	common.py \
	docs \
	doxygen \
	bin/git_sha1_gen.py \
	scons \
	SConstruct \
	build-support/conftest.dyn \
	build-support/conftest.map \
	meson.build \
	meson_options.txt \
	bin/meson.build \
	include/meson.build \
	bin/install_megadrivers.py \
	bin/meson_get_version.py

noinst_HEADERS = \
	include/c99_alloca.h \
	include/c99_compat.h \
	include/c99_math.h \
	include/c11 \
	include/drm-uapi/drm.h \
	include/drm-uapi/drm_fourcc.h \
	include/drm-uapi/drm_mode.h \
	include/drm-uapi/i915_drm.h \
	include/drm-uapi/tegra_drm.h \
	include/drm-uapi/v3d_drm.h \
	include/drm-uapi/vc4_drm.h \
	include/D3D9 \
	include/GL/wglext.h \
	include/HaikuGL \
	include/no_extern_c.h \
	include/pci_ids \
	include/vulkan

# We list some directories in EXTRA_DIST, but don't actually want to include
# the .gitignore files in the tarball.
dist-hook:
	find $(distdir) -name .gitignore -exec $(RM) {} +
