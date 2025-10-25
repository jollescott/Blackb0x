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

Blackb0x_INCLUDE_DIRS = -ILibraries -I../iBoot32Patcher

Blackb0x_LDFLAGS = -ldispatch -lirecovery-1.0 -limobiledevice-1.0 -lplist-2.0 -lfragmentzip

Blackb0x_HEADERS = Source/AppDelegate.h \
	Source/Blackb0x.h \
	Source/DeviceManager.h \
	Source/IPSW.h \
	Source/IPSWDownloader.h \
	Source/MainView.h \
	Source/Patcher.h 

Blackb0x_OBJC_PRECOMPILED_HEADERS = Blackb0x.pch

Blackb0x_OBJC_FILES = main.m \
	Source/AppDelegate.m \
	Source/Blackb0x.m \
	Source/DeviceManager.m \
	Source/MainView.m

Blackb0x_OBJCC_FILES = Source/IPSW.mm \
	Source/IPSWDownloader.mm \
	Source/Patcher.mm

Blackb0x_C_FILES = Libraries/libbootkit/libbootkit.c \
	Libraries/libiboot32patcher.c \
	Libraries/xpwntool.c \
	../CBPatcher/CBPatch.c \
	../CBPatcher/CBPatcher.c \
	../CBPatcher/CBPUtils.c \
	../iBoot32Patcher/functions.c \
	../iBoot32Patcher/patchers.c \
	../iBoot32Patcher/finders.c

Blackb0x_CFLAGS = -Wno-multichar -Wno-error=int-conversion

Blackb0x_RESOURCE_FILES = Info.plist

include GNUmakefile.preamble

include $(GNUSTEP_MAKEFILES)/application.make

include GNUmakefile.postamble
