# Simple Linux Character Driver
#A simple Linux character device driver built in C. Implements open, read, write, release. Creates /dev/virtual_device. Developed as part of low-level system programming practice.

Create an inode at master 301
```bash
sudo mknod -m 777 /dev/simple_char_device  c 301 0
```

View the inode successfully created:
```bash
ls -la /dev | grep simple_char_device
```

To install the driver,
In this repo folder run:
```bash
make
sudo insmod simple_char_driver.ko
```

View that the device installed:
```bash
cat /proc/devices | grep simple_driver
```

To test simply run the tester
```bash
./simple_char_test
```


To remove the driver
```bash
sudo rmmod simple_char_driver
```


