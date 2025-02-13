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
sudo dpkg -i libfprint.deb
```


support FT9769/FT9365/FT9391，
and FT9368/FT9338 will be support next.
