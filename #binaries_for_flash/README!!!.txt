esptool.py -p COM5 -b 460800 --before default_reset --after hard_reset --chip esp32s3 write_flash --flash_mode dio --flash_size 16MB --flash_freq 80m 0x0 build/bootloader/bootloader.bin 0x8000 build/partition_table/partition-table.bin 0x10000 build/projecthydra-32.bin 0x190000 build/storage.bin


bootloader.bin        → 0x0
partition-table.bin   → 0x8000
projecthydra-32.bin   → 0x10000
storage.bin           → 0x190000


in this example i use 'COM5' but you may need change to COMx (x = com port number)