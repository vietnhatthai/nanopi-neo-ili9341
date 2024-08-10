# ILI9341 Nanopi Neo Core/Core2

```
pi@nanopineo:~$ uname -a
Linux nanopineo 6.6.36-current-sunxi #1 SMP Thu Jun 27 11:49:15 UTC 2024 armv7l armv7l armv7l GNU/Linux
```

Wiring between ILI9341 and NanoPi Neo

```
3.3v  <-->  VCC & LED
GND   <-->  GND
PA14  <-->  SCK       & T_CLK    <SPI1>
PA16  <-->  SDO<MISO> & T_DO     <SPI1>
PA15  <-->  SDI<MOSI> & T_DIN    <SPI1>
PA1   <-->  DC
PG8   <-->  RESET
PA13  <-->  CS
PA17  <-->  T_CS
PG9   <-->  T_IRG
```

This is the /boot/armbianEnv.txt
```
overlays=spi1
param_spidev_spi_bus=1
param_spidev_spi_cs=1
param_spidev_spi_cs=0
user_overlays=fbtft-ili9341
```

Compile device tree
```
armbian-add-overlay /path/to/fbtft-ili9341.dts
```

Test

```
fbi -T 2 -d /dev/fb0 -a image.jpg
```


Hardware

[NanoPi NEO Core](https://www.friendlyelec.com/index.php?route=product/product&product_id=212&search=Neo+core&description=true&category_id=0)

[Mini Shield for NanoPi NEO Core/Core2](https://www.friendlyelec.com/index.php?route=product/product&product_id=213&search=Neo+core&description=true&category_id=0)

[2.8inch SPI Module ILI9341](http://www.lcdwiki.com/2.8inch_SPI_Module_ILI9341_SKU:MSP2807)

References

[Hackaday - Armbian, NanoPi and ILI9341 Touch](https://hackaday.io/project/190371-g-edm/log/217902-first-success-with-armbian-nanopi-and-ili9341-touch) 
