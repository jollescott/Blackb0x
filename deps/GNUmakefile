include $(GNUSTEP_MAKEFILES)/common.make

LIBRARY_NAME = CBPatcher iBoot32Patcher libfragmentzip libgeneral libirecovery xpwntool-swift

CBPatcher_C_FILES = CBPatcher/CBPatch.c \
	CBPatcher/CBPatcher.c \
	CBPatcher/CBPUtils.c

iBoot32Patcher_INCLUDE_DIRS = -I./iBoot32Patcher
iBoot32Patcher_C_FILES = iBoot32Patcher/finders.c \
	iBoot32Patcher/functions.c \
	iBoot32Patcher/iBoot32Patcher.c \
	iBoot32Patcher/patchers.c
iBoot32Patcher_CFLAGS = -Wno-error=int-conversion

libfragmentzip_INCLUDE_DIRS = -I./libgeneral/include -I./libfragmentzip/include
libfragmentzip_C_FILES = libfragmentzip/libfragmentzip/libfragmentzip.c

libgeneral_INCLUDE_DIRS = -I./libgeneral/include
libgeneral_CC_FILES = libgeneral/libgeneral/Event.cpp \
	libgeneral/libgeneral/exception.cpp \
	libgeneral/libgeneral/GuardAccess.cpp \
	libgeneral/libgeneral/Manager.cpp \
	libgeneral/libgeneral/Mem.cpp \
	libgeneral/libgeneral/Utils.cpp

libirecovery_C_FILES = libirecovery/src/libirecovery.c 
libirecovery_INCLUDE_DIRS = -I/usr/include/libusb-1.0 -I./libirecovery/include -I./libirecovery
libirecovery_LDFLAGS = -limobiledevice-1.0 -lusb-1.0
libirecovery_CFLAGS = -D HAVE_CONFIG_H

xpwntool-swift_INCLUDE_DIRS = -I./xpwntool-swift/includes
xpwntool-swift_C_FILES = xpwntool-swift/xpwntool.c \
	xpwntool-swift/libxpwn.c \
	xpwntool-swift/abstractfile.c \
	xpwntool-swift/nor_files.c \
	xpwntool-swift/img2.c \
	xpwntool-swift/img3.c \
	xpwntool-swift/lzssfile.c \
	xpwntool-swift/lzss.c 

include $(GNUSTEP_MAKEFILES)/library.make

include GNUmakefile.postamble