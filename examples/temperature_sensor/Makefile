PROGRAM = temperature_sensor

EXTRA_COMPONENTS = \
	extras/dht \
	extras/http-parser \
	$(abspath ../../components/common/wolfssl) \
	$(abspath ../../components/common/cJSON) \
	$(abspath ../../components/common/homekit)

# DHT11 sensor pin
SENSOR_PIN ?= 4

FLASH_SIZE ?= 32
FLASH_MODE = dio

EXTRA_CFLAGS += -I../.. -DHOMEKIT_SHORT_APPLE_UUIDS -DSENSOR_PIN=$(SENSOR_PIN)

include $(SDK_PATH)/common.mk

monitor:
	$(FILTEROUTPUT) --port $(ESPPORT) --baud 57600 --elf $(PROGRAM_OUT)
