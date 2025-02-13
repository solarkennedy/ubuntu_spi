build kernel driver:

Step 1:
install make&gcc 

```bash
sudo apt-get install make
sudo apt-get install gcc
```

step2 make&make install kernel driver

```bash
sudo make 
sudo make install
```

restart,then you can see a device as "/dev/focal_moh_spi"

step3 install libfprint.deb

```bash
sudo dpkg -i --force-overwrit libfprint-2-2_1.94.4+tod1-0ubuntu1~22.04.2_spi_20250112_amd64.deb
```

Notice:
```c
/*if spi transfer err,change line 493: spi->mode = SPI_MODE_0*/
	spi->mode = SPI_MODE_0|SPI_CS_HIGH;
support FT9769/FT9365/FT9391/FT9369，
and FT9368/FT9338 will be support next.
```
