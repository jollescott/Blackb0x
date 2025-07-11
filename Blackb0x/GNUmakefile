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

Blackb0x_INCLUDE_DIRS = -ILibraries

Blackb0x_LDFLAGS = -ldispatch -lirecovery-1.0 -limobiledevice-1.0 -lplist-2.0

Blackb0x_HEADERS = Source/AppDelegate.h \
	Source/Blackb0x.h \
	Source/IPSW.h \
	Source/IPSWDownloader.h \
	Source/DeviceManager.h

Blackb0x_OBJC_PRECOMPILED_HEADERS = Blackb0x.pch

Blackb0x_OBJC_FILES = main.m \
	Source/AppDelegate.m \
	Source/Blackb0x.m \
	Source/DeviceManager.m

Blackb0x_OBJCC_FILES = Source/IPSW.mm \
	Source/IPSWDownloader.mm \

Blackb0x_RESOURCE_FILES = Info.plist

include GNUmakefile.preamble

include $(GNUSTEP_MAKEFILES)/application.make

include GNUmakefile.postamble
