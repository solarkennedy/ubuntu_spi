# `focal_spi`: A Linux kernel driver for Focaltech SPI Fingerprint readers

## Building Manually

```bash
sudo apt-get update
sudo apt-get install build-essential

make 
sudo make install
```

## Building with DKMS

```bash
sudo apt-get update
sudo apt-get install build-essential dkms

sudo dkms add .
sudo dkms build focal_spi/1.0
sudo dkms install focal_spi/1.0
```

## Verify it worked

```
sudo dmesg | grep focal
...
ls -l /dev/focal_moh_spi
```

## Install modified libfprint

```bash
sudo dpkg -i --force-overwrite libfprint-2-2_1.94.4+tod1-0ubuntu1~22.04.2_spi_20250112_amd64.deb
```

Notice:
```c
/*if spi transfer err,change line 493: spi->mode = SPI_MODE_0*/
	spi->mode = SPI_MODE_0|SPI_CS_HIGH;
support FT9769/FT9365/FT9391/FT9369，
and FT9368/FT9338 will be support next.
```
