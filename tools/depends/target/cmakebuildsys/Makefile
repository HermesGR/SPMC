-include ../../Makefile.include

VERSION.TXT := $(CORE_SOURCE_DIR)/version.txt
APP_NAME=$(shell awk '/APP_NAME/ {print tolower($$2)}' $(VERSION.TXT))

ifeq ($(Configuration),)
  Configuration = Release
  ifeq ($(DEBUG_BUILD),yes)
    Configuration = Debug
  endif
endif

all:
	mkdir -p $(CORE_SOURCE_DIR)/build-$(CPU)
	cd $(CORE_SOURCE_DIR)/build-$(CPU); $(CMAKE) -DCMAKE_BUILD_TYPE=$(Configuration) -DENABLE_INTERNAL_CROSSGUID=OFF -DENABLE_INTERNAL_FFMPEG=OFF -DENABLE_AML=ON $(CORE_SOURCE_DIR)/project/cmake

clean:
	cd $(CORE_SOURCE_DIR)/build-$(CPU); $(MAKE) clean

distclean:
	cd $(CORE_SOURCE_DIR)/build-$(CPU); $(MAKE) clean
