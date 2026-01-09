ifeq ($(GNUSTEP_MAKEFILES),)
 GNUSTEP_MAKEFILES := $(shell gnustep-config --variable=GNUSTEP_MAKEFILES 2>/dev/null)
endif

ifeq ($(GNUSTEP_MAKEFILES),)
  $(error You need to run the GNUstep configuration script before compiling!)
endif

include $(GNUSTEP_MAKEFILES)/common.make

PACKAGE_NAME = Blackb0x
APP_NAME = Blackb0x

Blackb0x_OBJCFLAGS = -include Blackb0x.pch -Winvalid-pch -fobjc-runtime=gnustep-2 -fobjc-arc -fobjc-weak -fblocks

Blackb0x_INCLUDE_DIRS = -I./Libraries -I../iBoot32Patcher -I../xpwntool-swift/includes -I../libfragmentzip -I../libgeneral/include -I/usr/include/libusb-1.0/ -I../libirecovery

Blackb0x_LDFLAGS = -ldispatch -limobiledevice-1.0 -lplist-2.0 -lcrypto -lz -lcurl -lusb

Blackb0x_HEADERS = Source/AppDelegate.h \
	Source/Blackb0x.h \
	Source/checkm8.h \
	Source/DeviceManager.h \
	Source/IPSWDownloader.h \
	Source/IPSW.h \
	Source/IPSWDownloader.h \
	Source/MainView.h \
	Source/Patcher.h \
	Source/SHAtter.h \

Blackb0x_OBJC_PRECOMPILED_HEADERS = Blackb0x.pch

Blackb0x_OBJC_FILES = main.m \
	Source/AppDelegate.m \
	Source/Blackb0x.m \
	Source/DeviceManager.m \
	Source/MainView.m \
	Source/TaskManager.m

Blackb0x_OBJCC_FILES = Source/IPSW.mm \
	Source/IPSWDownloader.mm \
	Source/Patcher.mm

Blackb0x_C_FILES = Libraries/libbootkit/libbootkit.c \
	Libraries/libiboot32patcher.c \
	../xpwntool-swift/xpwntool.c \
	../xpwntool-swift/libxpwn.c \
	../xpwntool-swift/abstractfile.c \
	../xpwntool-swift/nor_files.c \
	../xpwntool-swift/img2.c \
	../xpwntool-swift/img3.c \
	../xpwntool-swift/lzssfile.c \
	../xpwntool-swift/lzss.c \
	../CBPatcher/CBPatch.c \
	../CBPatcher/CBPUtils.c \
	Libraries/CBPatcher.c \
	../iBoot32Patcher/functions.c \
	../iBoot32Patcher/patchers.c \
	../iBoot32Patcher/finders.c \
	../libfragmentzip/libfragmentzip/libfragmentzip.c \
	../libirecovery/src/libirecovery.c \

Blackb0x_CFLAGS = -Wno-multichar -Wno-error=int-conversion

Blackb0x_RESOURCE_FILES = Info.plist \
	Assets.xcassets \
	Base.lproj/MainMenu.xib 

include GNUmakefile.preamble

include $(GNUSTEP_MAKEFILES)/application.make

include GNUmakefile.postamble
