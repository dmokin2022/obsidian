


Как подключить переходник [[Преобразователи USB - I2C, SPI, UART, JTAG]] к компьютеру и использовать через [[Python]]

1. install [[PyCharm]] pycharm-community;
1.1 new project from vcs via url https://github.com/karlp/ch341-py2c.git;
1.2 configure interpreter python3.12;

Ввести через консоль:
	pip install usb;
	pip install pyusb;
	pip install pyusb-libusb1-backend;

1.3 in console: 
1.3.1 pip install usb;
1.3.2 pip install pyusb;
1.3.3 pip install pyusb-libusb1-backend;
2. install ch341a driver: https://kit.alexgyver.ru/tutorials/driver-install/;
3. install libusb driver: https://technical.swissmicros.com/doc/libusb_install/libusb_install.html;
4. run quick.py in pycharm;
4.1 have fun!