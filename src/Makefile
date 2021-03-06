# ------------------------------------------------------------------------------
#
# Makefile for the LDD-LinuxDeviceDrivers.
#
# Author: dnatividade
# Create: 2016-07-29 15:50:46
# Adapted: 2018-12-13
# Last modified: 2018-12-14 00:00:00
# Description:
# 	This program is loaded as a kernel(v2.6.18 or later) module.
# 	Tested in kernel v4.9.0.
# 	Use "make install" to load it into kernel.
# 	Use "make remove" to remove the module out of kernel.
#
# ------------------------------------------------------------------------------


#my driver description
DRIVER_VERSION := "1.0.0"
DRIVER_AUTHOR  := "Diego Natividade"
DRIVER_DESC    := "Linux Arduino-as-network Driver"
DRIVER_LICENSE := "GPL"


MODULE_NAME := naive_usb



ifneq ($(KERNELRELEASE),)	# kernelspace

obj-m := $(MODULE_NAME).o

else				# userspace


LINUX_KERNEL := $(shell uname -r)
LINUX_KERNEL_PATH := /lib/modules/$(LINUX_KERNEL)/build

CURRENT_PATH := $(shell pwd)
CFG_INC := $(CURRENT_PATH)
MODCFLAGS := -O2 -Wall -DMODULE -D__KERNEL__ -DLINUX -std=c99
EXTRA_CFLAGS  += $(MODULE_FLAGS) -I $(CFG_INC)


modules:
	make -C $(LINUX_KERNEL_PATH) M=$(CURRENT_PATH) modules

modules_install:
	make -C $(LINUX_KERNEL_PATH) M=$(CURRENT_PATH) modules_install

insmod:
	sudo insmod $(MODULE_NAME).ko

reinsmod:
	sudo rmmod $(MODULE_NAME)
	sudo insmod $(MODULE_NAME).ko

github:
	cd $(ROOT) && make github

rmmod:
	sudo rmmod $(MODULE_NAME)

test :
	sudo ../injector/memInjector -l stack -m random -t word_0 --time 1 --timeout 3 -p 1

clean:
	make -C $(LINUX_KERNEL_PATH) M=$(CURRENT_PATH) clean
	rm -f modules.order Module.symvers Module.markers

.PHNOY:
	modules modules_install clean



endif

