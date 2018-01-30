# fb-vncserver

VNC server for Linux framebuffer devices.

The goal is to check remote embedded Linux systems without X, so only the remote display is implemented.
(no input, no file transfer,..)

The code is based on a LibVNC example for Android:
https://github.com/LibVNC/libvncserver/blob/master/examples/androidvncserver.c

All input handling was removed, command-line parameters port and fbdev were added.
32 bit color support was added.

### build

Dependency:

    libvncserver:

    https://github.com/LibVNC/libvncserver.git

    Compile:
    mkdir build
    cd build
    cmake .. -DCMAKE_INSTALL_PREFIX=[INSTALL_PATH]
    make && make install

Using cmake:

	mkdir -p build && cd build
	cmake ..
	make

### command-line help

	# fb-vncserver -h
	fb-vncserver [-f device] [-p port] [-h]
	-p port: VNC port, default is 5900
	-f device: framebuffer device node, default is /dev/fb0
	-h : print this help
