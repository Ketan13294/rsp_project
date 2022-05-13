# RSP Final Project: Turtlebot Follow the Leader
Kapi Ketan Mehta, Michael Wilkinson, Brian Woronowicz
------------------------------------------------

Repo for Spring 2022 RSP Course Project.
For this project, we produced the code necessary to have a turtlebot use its raspicam to detect and follow a fiducial marker (AR tag), both in real life and in gazebo. 
''' #bash
├── aruco_detect
│   ├── cfg
│   │   └── DetectorParams.cfg
│   ├── CHANGELOG.rst
│   ├── CMakeLists.txt
│   ├── launch
│   │   └── aruco_detect.launch
│   ├── package.xml
│   ├── README.md
│   ├── scripts
│   │   ├── create_markers.py
│   │   └── marker_generation
│   │       ├── __init__.py
│   │       └── marker_gen.py
│   ├── setup.py
│   ├── src
│   │   └── aruco_detect.cpp
│   └── test
│       ├── aruco_images.test
│       ├── aruco_images_test.cpp
│       └── test_images
│           ├── tag_01_d7_14cm.png
│           ├── tag_245-246_d7_14cm.png
│           └── test.pdf
├── DynamixelSDK
│   ├── c
│   │   ├── build
│   │   │   ├── linux32
│   │   │   │   └── Makefile
│   │   │   ├── linux64
│   │   │   │   └── Makefile
│   │   │   ├── linux_sbc
│   │   │   │   └── Makefile
│   │   │   ├── mac
│   │   │   │   └── Makefile
│   │   │   ├── win32
│   │   │   │   ├── dxl_x86_c
│   │   │   │   │   ├── dxl_x86_c.vcxproj
│   │   │   │   │   ├── dxl_x86_c.vcxproj.filters
│   │   │   │   │   └── dxl_x86_c.vcxproj.user
│   │   │   │   ├── dxl_x86_c.sln
│   │   │   │   └── output
│   │   │   │       ├── dxl_x86_c.dll
│   │   │   │       └── dxl_x86_c.lib
│   │   │   └── win64
│   │   │       ├── dxl_x64_c
│   │   │       │   ├── dxl_x64_c.vcxproj
│   │   │       │   ├── dxl_x64_c.vcxproj.filters
│   │   │       │   └── dxl_x64_c.vcxproj.user
│   │   │       ├── dxl_x64_c.sln
│   │   │       └── output
│   │   │           ├── dxl_x64_c.dll
│   │   │           └── dxl_x64_c.lib
│   │   ├── example
│   │   │   ├── dxl_monitor
│   │   │   │   ├── dxl_monitor.c
│   │   │   │   ├── linux32
│   │   │   │   │   └── Makefile
│   │   │   │   ├── linux64
│   │   │   │   │   └── Makefile
│   │   │   │   ├── linux_sbc
│   │   │   │   │   └── Makefile
│   │   │   │   ├── mac
│   │   │   │   │   └── Makefile
│   │   │   │   ├── win32
│   │   │   │   │   ├── dxl_monitor
│   │   │   │   │   │   ├── dxl_monitor.vcxproj
│   │   │   │   │   │   ├── dxl_monitor.vcxproj.filters
│   │   │   │   │   │   └── dxl_monitor.vcxproj.user
│   │   │   │   │   └── dxl_monitor.sln
│   │   │   │   └── win64
│   │   │   │       ├── dxl_monitor
│   │   │   │       │   ├── dxl_monitor.vcxproj
│   │   │   │       │   ├── dxl_monitor.vcxproj.filters
│   │   │   │       │   └── dxl_monitor.vcxproj.user
│   │   │   │       └── dxl_monitor.sln
│   │   │   ├── protocol1.0
│   │   │   │   ├── bulk_read
│   │   │   │   │   ├── bulk_read.c
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── bulk_read
│   │   │   │   │   │   │   ├── bulk_read.vcxproj
│   │   │   │   │   │   │   ├── bulk_read.vcxproj.filters
│   │   │   │   │   │   │   └── bulk_read.vcxproj.user
│   │   │   │   │   │   └── bulk_read.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── bulk_read
│   │   │   │   │       │   ├── bulk_read.vcxproj
│   │   │   │   │       │   ├── bulk_read.vcxproj.filters
│   │   │   │   │       │   └── bulk_read.vcxproj.user
│   │   │   │   │       └── bulk_read.sln
│   │   │   │   ├── multi_port
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── multi_port.c
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── multi_port
│   │   │   │   │   │   │   ├── multi_port.vcxproj
│   │   │   │   │   │   │   ├── multi_port.vcxproj.filters
│   │   │   │   │   │   │   └── multi_port.vcxproj.user
│   │   │   │   │   │   └── multi_port.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── multi_port
│   │   │   │   │       │   ├── multi_port.vcxproj
│   │   │   │   │       │   ├── multi_port.vcxproj.filters
│   │   │   │   │       │   └── multi_port.vcxproj.user
│   │   │   │   │       └── multi_port.sln
│   │   │   │   ├── ping
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── ping.c
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── ping
│   │   │   │   │   │   │   ├── ping.vcxproj
│   │   │   │   │   │   │   ├── ping.vcxproj.filters
│   │   │   │   │   │   │   └── ping.vcxproj.user
│   │   │   │   │   │   └── ping.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── ping
│   │   │   │   │       │   ├── ping.vcxproj
│   │   │   │   │       │   ├── ping.vcxproj.filters
│   │   │   │   │       │   └── ping.vcxproj.user
│   │   │   │   │       └── ping.sln
│   │   │   │   ├── read_write
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── read_write.c
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── read_write
│   │   │   │   │   │   │   ├── read_write.vcxproj
│   │   │   │   │   │   │   ├── read_write.vcxproj.filters
│   │   │   │   │   │   │   └── read_write.vcxproj.user
│   │   │   │   │   │   └── read_write.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── read_write
│   │   │   │   │       │   ├── read_write.vcxproj
│   │   │   │   │       │   ├── read_write.vcxproj.filters
│   │   │   │   │       │   └── read_write.vcxproj.user
│   │   │   │   │       └── read_write.sln
│   │   │   │   ├── reset
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── reset.c
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── reset
│   │   │   │   │   │   │   ├── reset.vcxproj
│   │   │   │   │   │   │   ├── reset.vcxproj.filters
│   │   │   │   │   │   │   └── reset.vcxproj.user
│   │   │   │   │   │   └── reset.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── reset
│   │   │   │   │       │   ├── reset.vcxproj
│   │   │   │   │       │   ├── reset.vcxproj.filters
│   │   │   │   │       │   └── reset.vcxproj.user
│   │   │   │   │       └── reset.sln
│   │   │   │   └── sync_write
│   │   │   │       ├── linux32
│   │   │   │       │   └── Makefile
│   │   │   │       ├── linux64
│   │   │   │       │   └── Makefile
│   │   │   │       ├── linux_sbc
│   │   │   │       │   └── Makefile
│   │   │   │       ├── mac
│   │   │   │       │   └── Makefile
│   │   │   │       ├── sync_write.c
│   │   │   │       ├── win32
│   │   │   │       │   ├── sync_write
│   │   │   │       │   │   ├── sync_write.vcxproj
│   │   │   │       │   │   ├── sync_write.vcxproj.filters
│   │   │   │       │   │   └── sync_write.vcxproj.user
│   │   │   │       │   └── sync_write.sln
│   │   │   │       └── win64
│   │   │   │           ├── sync_write
│   │   │   │           │   ├── sync_write.vcxproj
│   │   │   │           │   ├── sync_write.vcxproj.filters
│   │   │   │           │   └── sync_write.vcxproj.user
│   │   │   │           └── sync_write.sln
│   │   │   ├── protocol2.0
│   │   │   │   ├── broadcast_ping
│   │   │   │   │   ├── broadcast_ping.c
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── broadcast_ping
│   │   │   │   │   │   │   ├── broadcast_ping.vcxproj
│   │   │   │   │   │   │   ├── broadcast_ping.vcxproj.filters
│   │   │   │   │   │   │   └── broadcast_ping.vcxproj.user
│   │   │   │   │   │   └── broadcast_ping.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── broadcast_ping
│   │   │   │   │       │   ├── broadcast_ping.vcxproj
│   │   │   │   │       │   ├── broadcast_ping.vcxproj.filters
│   │   │   │   │       │   └── broadcast_ping.vcxproj.user
│   │   │   │   │       └── broadcast_ping.sln
│   │   │   │   ├── bulk_read_write
│   │   │   │   │   ├── bulk_read_write.c
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── bulk_read_write
│   │   │   │   │   │   │   ├── bulk_read_write.vcxproj
│   │   │   │   │   │   │   ├── bulk_read_write.vcxproj.filters
│   │   │   │   │   │   │   └── bulk_read_write.vcxproj.user
│   │   │   │   │   │   └── bulk_read_write.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── bulk_read_write
│   │   │   │   │       │   ├── bulk_read_write.vcxproj
│   │   │   │   │       │   ├── bulk_read_write.vcxproj.filters
│   │   │   │   │       │   └── bulk_read_write.vcxproj.user
│   │   │   │   │       └── bulk_read_write.sln
│   │   │   │   ├── clear_multi_turn
│   │   │   │   │   ├── clear_multi_turn.c
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── clear_multi_turn
│   │   │   │   │   │   │   ├── clear_multi_turn.vcxproj
│   │   │   │   │   │   │   ├── clear_multi_turn.vcxproj.filters
│   │   │   │   │   │   │   └── clear_multi_turn.vcxproj.user
│   │   │   │   │   │   └── clear_multi_turn.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── clear_multi_turn
│   │   │   │   │       │   ├── clear_multi_turn.vcxproj
│   │   │   │   │       │   ├── clear_multi_turn.vcxproj.filters
│   │   │   │   │       │   └── clear_multi_turn.vcxproj.user
│   │   │   │   │       └── clear_multi_turn.sln
│   │   │   │   ├── factory_reset
│   │   │   │   │   ├── factory_reset.c
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── factory_reset
│   │   │   │   │   │   │   ├── factory_reset.vcxproj
│   │   │   │   │   │   │   ├── factory_reset.vcxproj.filters
│   │   │   │   │   │   │   └── factory_reset.vcxproj.user
│   │   │   │   │   │   └── factory_reset.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── factory_reset
│   │   │   │   │       │   ├── factory_reset.vcxproj
│   │   │   │   │       │   ├── factory_reset.vcxproj.filters
│   │   │   │   │       │   └── factory_reset.vcxproj.user
│   │   │   │   │       └── factory_reset.sln
│   │   │   │   ├── indirect_address
│   │   │   │   │   ├── indirect_address.c
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   ├── indirect_address
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── indirect_address
│   │   │   │   │   │   │   ├── indirect_address.vcxproj
│   │   │   │   │   │   │   ├── indirect_address.vcxproj.filters
│   │   │   │   │   │   │   └── indirect_address.vcxproj.user
│   │   │   │   │   │   └── indirect_address.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── indirect_address
│   │   │   │   │       │   ├── indirect_address.vcxproj
│   │   │   │   │       │   ├── indirect_address.vcxproj.filters
│   │   │   │   │       │   └── indirect_address.vcxproj.user
│   │   │   │   │       └── indirect_address.sln
│   │   │   │   ├── multi_port
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── multi_port.c
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── multi_port
│   │   │   │   │   │   │   ├── multi_port.vcxproj
│   │   │   │   │   │   │   ├── multi_port.vcxproj.filters
│   │   │   │   │   │   │   └── multi_port.vcxproj.user
│   │   │   │   │   │   └── multi_port.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── multi_port
│   │   │   │   │       │   ├── multi_port.vcxproj
│   │   │   │   │       │   ├── multi_port.vcxproj.filters
│   │   │   │   │       │   └── multi_port.vcxproj.user
│   │   │   │   │       └── multi_port.sln
│   │   │   │   ├── ping
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── ping.c
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── ping
│   │   │   │   │   │   │   ├── ping.vcxproj
│   │   │   │   │   │   │   ├── ping.vcxproj.filters
│   │   │   │   │   │   │   └── ping.vcxproj.user
│   │   │   │   │   │   └── ping.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── ping
│   │   │   │   │       │   ├── ping.vcxproj
│   │   │   │   │       │   ├── ping.vcxproj.filters
│   │   │   │   │       │   └── ping.vcxproj.user
│   │   │   │   │       └── ping.sln
│   │   │   │   ├── read_write
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   ├── Makefile
│   │   │   │   │   │   └── read_write
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── read_write.c
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── read_write
│   │   │   │   │   │   │   ├── read_write.vcxproj
│   │   │   │   │   │   │   ├── read_write.vcxproj.filters
│   │   │   │   │   │   │   └── read_write.vcxproj.user
│   │   │   │   │   │   └── read_write.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── read_write
│   │   │   │   │       │   ├── read_write.vcxproj
│   │   │   │   │       │   ├── read_write.vcxproj.filters
│   │   │   │   │       │   └── read_write.vcxproj.user
│   │   │   │   │       └── read_write.sln
│   │   │   │   ├── reboot
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── reboot.c
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── reboot
│   │   │   │   │   │   │   ├── reboot.vcxproj
│   │   │   │   │   │   │   ├── reboot.vcxproj.filters
│   │   │   │   │   │   │   └── reboot.vcxproj.user
│   │   │   │   │   │   └── reboot.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── reboot
│   │   │   │   │       │   ├── reboot.vcxproj
│   │   │   │   │       │   ├── reboot.vcxproj.filters
│   │   │   │   │       │   └── reboot.vcxproj.user
│   │   │   │   │       └── reboot.sln
│   │   │   │   └── sync_read_write
│   │   │   │       ├── linux32
│   │   │   │       │   └── Makefile
│   │   │   │       ├── linux64
│   │   │   │       │   └── Makefile
│   │   │   │       ├── linux_sbc
│   │   │   │       │   └── Makefile
│   │   │   │       ├── mac
│   │   │   │       │   └── Makefile
│   │   │   │       ├── sync_read_write.c
│   │   │   │       ├── win32
│   │   │   │       │   ├── sync_read_write
│   │   │   │       │   │   ├── sync_read_write.vcxproj
│   │   │   │       │   │   ├── sync_read_write.vcxproj.filters
│   │   │   │       │   │   └── sync_read_write.vcxproj.user
│   │   │   │       │   └── sync_read_write.sln
│   │   │   │       └── win64
│   │   │   │           ├── sync_read_write
│   │   │   │           │   ├── sync_read_write.vcxproj
│   │   │   │           │   ├── sync_read_write.vcxproj.filters
│   │   │   │           │   └── sync_read_write.vcxproj.user
│   │   │   │           └── sync_read_write.sln
│   │   │   └── protocol_combined
│   │   │       ├── linux32
│   │   │       │   └── Makefile
│   │   │       ├── linux64
│   │   │       │   └── Makefile
│   │   │       ├── linux_sbc
│   │   │       │   └── Makefile
│   │   │       ├── mac
│   │   │       │   └── Makefile
│   │   │       ├── protocol_combined.c
│   │   │       ├── win32
│   │   │       │   ├── protocol_combined
│   │   │       │   │   ├── protocol_combined.vcxproj
│   │   │       │   │   ├── protocol_combined.vcxproj.filters
│   │   │       │   │   └── protocol_combined.vcxproj.user
│   │   │       │   └── protocol_combined.sln
│   │   │       └── win64
│   │   │           ├── protocol_combined
│   │   │           │   ├── protocol_combined.vcxproj
│   │   │           │   ├── protocol_combined.vcxproj.filters
│   │   │           │   └── protocol_combined.vcxproj.user
│   │   │           └── protocol_combined.sln
│   │   ├── include
│   │   │   └── dynamixel_sdk
│   │   │       ├── dynamixel_sdk.h
│   │   │       ├── group_bulk_read.h
│   │   │       ├── group_bulk_write.h
│   │   │       ├── group_sync_read.h
│   │   │       ├── group_sync_write.h
│   │   │       ├── packet_handler.h
│   │   │       ├── port_handler.h
│   │   │       ├── port_handler_linux.h
│   │   │       ├── port_handler_mac.h
│   │   │       ├── port_handler_windows.h
│   │   │       ├── protocol1_packet_handler.h
│   │   │       ├── protocol2_packet_handler.h
│   │   │       └── robotis_def.h
│   │   └── src
│   │       └── dynamixel_sdk
│   │           ├── group_bulk_read.c
│   │           ├── group_bulk_write.c
│   │           ├── group_sync_read.c
│   │           ├── group_sync_write.c
│   │           ├── packet_handler.c
│   │           ├── port_handler.c
│   │           ├── port_handler_linux.c
│   │           ├── port_handler_mac.c
│   │           ├── port_handler_windows.c
│   │           ├── protocol1_packet_handler.c
│   │           └── protocol2_packet_handler.c
│   ├── c#
│   │   ├── dynamixel_functions_csharp
│   │   │   ├── win32
│   │   │   │   └── dynamixel.cs
│   │   │   └── win64
│   │   │       └── dynamixel.cs
│   │   ├── protocol1.0
│   │   │   ├── bulk_read
│   │   │   │   ├── win32
│   │   │   │   │   ├── bulk_read
│   │   │   │   │   │   ├── App.config
│   │   │   │   │   │   ├── BulkRead.cs
│   │   │   │   │   │   ├── bulk_read.csproj
│   │   │   │   │   │   ├── dynamixel.cs
│   │   │   │   │   │   └── Properties
│   │   │   │   │   │       └── AssemblyInfo.cs
│   │   │   │   │   └── bulk_read.sln
│   │   │   │   └── win64
│   │   │   │       ├── bulk_read
│   │   │   │       │   ├── App.config
│   │   │   │       │   ├── BulkRead.cs
│   │   │   │       │   ├── bulk_read.csproj
│   │   │   │       │   ├── dynamixel.cs
│   │   │   │       │   └── Properties
│   │   │   │       │       └── AssemblyInfo.cs
│   │   │   │       └── bulk_read.sln
│   │   │   ├── multi_port
│   │   │   │   ├── win32
│   │   │   │   │   ├── multi_port
│   │   │   │   │   │   ├── App.config
│   │   │   │   │   │   ├── dynamixel.cs
│   │   │   │   │   │   ├── MultiPort.cs
│   │   │   │   │   │   ├── multi_port.csproj
│   │   │   │   │   │   └── Properties
│   │   │   │   │   │       └── AssemblyInfo.cs
│   │   │   │   │   └── multi_port.sln
│   │   │   │   └── win64
│   │   │   │       ├── multi_port
│   │   │   │       │   ├── App.config
│   │   │   │       │   ├── dynamixel.cs
│   │   │   │       │   ├── MultiPort.cs
│   │   │   │       │   ├── multi_port.csproj
│   │   │   │       │   └── Properties
│   │   │   │       │       └── AssemblyInfo.cs
│   │   │   │       └── multi_port.sln
│   │   │   ├── ping
│   │   │   │   ├── win32
│   │   │   │   │   ├── ping
│   │   │   │   │   │   ├── App.config
│   │   │   │   │   │   ├── dynamixel.cs
│   │   │   │   │   │   ├── Ping.cs
│   │   │   │   │   │   ├── ping.csproj
│   │   │   │   │   │   └── Properties
│   │   │   │   │   │       └── AssemblyInfo.cs
│   │   │   │   │   └── ping.sln
│   │   │   │   └── win64
│   │   │   │       ├── ping
│   │   │   │       │   ├── App.config
│   │   │   │       │   ├── dynamixel.cs
│   │   │   │       │   ├── Ping.cs
│   │   │   │       │   ├── ping.csproj
│   │   │   │       │   └── Properties
│   │   │   │       │       └── AssemblyInfo.cs
│   │   │   │       └── ping.sln
│   │   │   ├── read_write
│   │   │   │   ├── win32
│   │   │   │   │   ├── read_write
│   │   │   │   │   │   ├── App.config
│   │   │   │   │   │   ├── dynamixel.cs
│   │   │   │   │   │   ├── Properties
│   │   │   │   │   │   │   └── AssemblyInfo.cs
│   │   │   │   │   │   ├── ReadWrite.cs
│   │   │   │   │   │   ├── read_write.csproj
│   │   │   │   │   │   └── read_write.csproj.user
│   │   │   │   │   └── read_write.sln
│   │   │   │   └── win64
│   │   │   │       ├── read_write
│   │   │   │       │   ├── App.config
│   │   │   │       │   ├── dynamixel.cs
│   │   │   │       │   ├── Properties
│   │   │   │       │   │   └── AssemblyInfo.cs
│   │   │   │       │   ├── ReadWrite.cs
│   │   │   │       │   ├── read_write.csproj
│   │   │   │       │   └── read_write.csproj.user
│   │   │   │       └── read_write.sln
│   │   │   ├── reset
│   │   │   │   ├── win32
│   │   │   │   │   ├── reset
│   │   │   │   │   │   ├── App.config
│   │   │   │   │   │   ├── dynamixel.cs
│   │   │   │   │   │   ├── Properties
│   │   │   │   │   │   │   └── AssemblyInfo.cs
│   │   │   │   │   │   ├── Reset.cs
│   │   │   │   │   │   └── reset.csproj
│   │   │   │   │   └── reset.sln
│   │   │   │   └── win64
│   │   │   │       ├── reset
│   │   │   │       │   ├── App.config
│   │   │   │       │   ├── dynamixel.cs
│   │   │   │       │   ├── Properties
│   │   │   │       │   │   └── AssemblyInfo.cs
│   │   │   │       │   ├── Reset.cs
│   │   │   │       │   └── reset.csproj
│   │   │   │       └── reset.sln
│   │   │   └── sync_write
│   │   │       ├── win32
│   │   │       │   ├── sync_write
│   │   │       │   │   ├── App.config
│   │   │       │   │   ├── dynamixel.cs
│   │   │       │   │   ├── Properties
│   │   │       │   │   │   └── AssemblyInfo.cs
│   │   │       │   │   ├── SyncWrite.cs
│   │   │       │   │   └── sync_write.csproj
│   │   │       │   └── sync_write.sln
│   │   │       └── win64
│   │   │           ├── sync_write
│   │   │           │   ├── App.config
│   │   │           │   ├── dynamixel.cs
│   │   │           │   ├── Properties
│   │   │           │   │   └── AssemblyInfo.cs
│   │   │           │   ├── SyncWrite.cs
│   │   │           │   └── sync_write.csproj
│   │   │           └── sync_write.sln
│   │   ├── protocol2.0
│   │   │   ├── broadcast_ping
│   │   │   │   ├── win32
│   │   │   │   │   ├── broadcast_ping
│   │   │   │   │   │   ├── App.config
│   │   │   │   │   │   ├── BroadcastPing.cs
│   │   │   │   │   │   ├── broadcast_ping.csproj
│   │   │   │   │   │   ├── dynamixel.cs
│   │   │   │   │   │   └── Properties
│   │   │   │   │   │       └── AssemblyInfo.cs
│   │   │   │   │   └── broadcast_ping.sln
│   │   │   │   └── win64
│   │   │   │       ├── broadcast_ping
│   │   │   │       │   ├── App.config
│   │   │   │       │   ├── BroadcastPing.cs
│   │   │   │       │   ├── broadcast_ping.csproj
│   │   │   │       │   ├── dynamixel.cs
│   │   │   │       │   └── Properties
│   │   │   │       │       └── AssemblyInfo.cs
│   │   │   │       └── broadcast_ping.sln
│   │   │   ├── bulk_read_write
│   │   │   │   ├── win32
│   │   │   │   │   ├── bulk_read_write
│   │   │   │   │   │   ├── App.config
│   │   │   │   │   │   ├── BulkReadWrite.cs
│   │   │   │   │   │   ├── bulk_read_write.csproj
│   │   │   │   │   │   ├── dynamixel.cs
│   │   │   │   │   │   └── Properties
│   │   │   │   │   │       └── AssemblyInfo.cs
│   │   │   │   │   └── bulk_read_write.sln
│   │   │   │   └── win64
│   │   │   │       ├── bulk_read_write
│   │   │   │       │   ├── App.config
│   │   │   │       │   ├── BulkReadWrite.cs
│   │   │   │       │   ├── bulk_read_write.csproj
│   │   │   │       │   ├── dynamixel.cs
│   │   │   │       │   └── Properties
│   │   │   │       │       └── AssemblyInfo.cs
│   │   │   │       └── bulk_read_write.sln
│   │   │   ├── clear_multi_turn
│   │   │   │   ├── win32
│   │   │   │   │   ├── clear_multi_turn
│   │   │   │   │   │   ├── App.config
│   │   │   │   │   │   ├── ClearMultiTurn.cs
│   │   │   │   │   │   ├── clear_multi_turn.csproj
│   │   │   │   │   │   ├── dynamixel.cs
│   │   │   │   │   │   └── Properties
│   │   │   │   │   │       └── AssemblyInfo.cs
│   │   │   │   │   └── clear_multi_turn.sln
│   │   │   │   └── win64
│   │   │   │       ├── clear_multi_turn
│   │   │   │       │   ├── App.config
│   │   │   │       │   ├── ClearMultiTurn.cs
│   │   │   │       │   ├── clear_multi_turn.csproj
│   │   │   │       │   ├── dynamixel.cs
│   │   │   │       │   └── Properties
│   │   │   │       │       └── AssemblyInfo.cs
│   │   │   │       └── clear_multi_turn.sln
│   │   │   ├── factory_reset
│   │   │   │   ├── win32
│   │   │   │   │   ├── factory_reset
│   │   │   │   │   │   ├── App.config
│   │   │   │   │   │   ├── dynamixel.cs
│   │   │   │   │   │   ├── FactoryReset.cs
│   │   │   │   │   │   ├── factory_reset.csproj
│   │   │   │   │   │   └── Properties
│   │   │   │   │   │       └── AssemblyInfo.cs
│   │   │   │   │   └── factory_reset.sln
│   │   │   │   └── win64
│   │   │   │       ├── factory_reset
│   │   │   │       │   ├── App.config
│   │   │   │       │   ├── dynamixel.cs
│   │   │   │       │   ├── FactoryReset.cs
│   │   │   │       │   ├── factory_reset.csproj
│   │   │   │       │   └── Properties
│   │   │   │       │       └── AssemblyInfo.cs
│   │   │   │       └── factory_reset.sln
│   │   │   ├── indirect_address
│   │   │   │   ├── win32
│   │   │   │   │   ├── indirect_address
│   │   │   │   │   │   ├── App.config
│   │   │   │   │   │   ├── dynamixel.cs
│   │   │   │   │   │   ├── IndirectAddress.cs
│   │   │   │   │   │   ├── indirect_address.csproj
│   │   │   │   │   │   └── Properties
│   │   │   │   │   │       └── AssemblyInfo.cs
│   │   │   │   │   └── indirect_address.sln
│   │   │   │   └── win64
│   │   │   │       ├── indirect_address
│   │   │   │       │   ├── App.config
│   │   │   │       │   ├── dynamixel.cs
│   │   │   │       │   ├── IndirectAddress.cs
│   │   │   │       │   ├── indirect_address.csproj
│   │   │   │       │   └── Properties
│   │   │   │       │       └── AssemblyInfo.cs
│   │   │   │       └── indirect_address.sln
│   │   │   ├── multi_port
│   │   │   │   ├── win32
│   │   │   │   │   ├── multi_port
│   │   │   │   │   │   ├── App.config
│   │   │   │   │   │   ├── dynamixel.cs
│   │   │   │   │   │   ├── MultiPort.cs
│   │   │   │   │   │   ├── multi_port.csproj
│   │   │   │   │   │   └── Properties
│   │   │   │   │   │       └── AssemblyInfo.cs
│   │   │   │   │   └── multi_port.sln
│   │   │   │   └── win64
│   │   │   │       ├── multi_port
│   │   │   │       │   ├── App.config
│   │   │   │       │   ├── dynamixel.cs
│   │   │   │       │   ├── MultiPort.cs
│   │   │   │       │   ├── multi_port.csproj
│   │   │   │       │   └── Properties
│   │   │   │       │       └── AssemblyInfo.cs
│   │   │   │       └── multi_port.sln
│   │   │   ├── ping
│   │   │   │   ├── win32
│   │   │   │   │   ├── ping
│   │   │   │   │   │   ├── App.config
│   │   │   │   │   │   ├── dynamixel.cs
│   │   │   │   │   │   ├── Ping.cs
│   │   │   │   │   │   ├── ping.csproj
│   │   │   │   │   │   └── Properties
│   │   │   │   │   │       └── AssemblyInfo.cs
│   │   │   │   │   └── ping.sln
│   │   │   │   └── win64
│   │   │   │       ├── ping
│   │   │   │       │   ├── App.config
│   │   │   │       │   ├── dynamixel.cs
│   │   │   │       │   ├── Ping.cs
│   │   │   │       │   ├── ping.csproj
│   │   │   │       │   └── Properties
│   │   │   │       │       └── AssemblyInfo.cs
│   │   │   │       └── ping.sln
│   │   │   ├── read_write
│   │   │   │   ├── win32
│   │   │   │   │   ├── read_write
│   │   │   │   │   │   ├── App.config
│   │   │   │   │   │   ├── dynamixel.cs
│   │   │   │   │   │   ├── Properties
│   │   │   │   │   │   │   └── AssemblyInfo.cs
│   │   │   │   │   │   ├── ReadWrite.cs
│   │   │   │   │   │   ├── read_write.csproj
│   │   │   │   │   │   └── read_write.csproj.user
│   │   │   │   │   └── read_write.sln
│   │   │   │   └── win64
│   │   │   │       ├── read_write
│   │   │   │       │   ├── App.config
│   │   │   │       │   ├── dynamixel.cs
│   │   │   │       │   ├── Properties
│   │   │   │       │   │   └── AssemblyInfo.cs
│   │   │   │       │   ├── ReadWrite.cs
│   │   │   │       │   ├── read_write.csproj
│   │   │   │       │   └── read_write.csproj.user
│   │   │   │       └── read_write.sln
│   │   │   ├── reboot
│   │   │   │   ├── win32
│   │   │   │   │   ├── reboot
│   │   │   │   │   │   ├── App.config
│   │   │   │   │   │   ├── dynamixel.cs
│   │   │   │   │   │   ├── Properties
│   │   │   │   │   │   │   └── AssemblyInfo.cs
│   │   │   │   │   │   ├── Reboot.cs
│   │   │   │   │   │   └── reboot.csproj
│   │   │   │   │   └── reboot.sln
│   │   │   │   └── win64
│   │   │   │       ├── reboot
│   │   │   │       │   ├── App.config
│   │   │   │       │   ├── dynamixel.cs
│   │   │   │       │   ├── Properties
│   │   │   │       │   │   └── AssemblyInfo.cs
│   │   │   │       │   ├── Reboot.cs
│   │   │   │       │   └── reboot.csproj
│   │   │   │       └── reboot.sln
│   │   │   └── sync_read_write
│   │   │       ├── win32
│   │   │       │   ├── sync_read_write
│   │   │       │   │   ├── App.config
│   │   │       │   │   ├── dynamixel.cs
│   │   │       │   │   ├── Properties
│   │   │       │   │   │   └── AssemblyInfo.cs
│   │   │       │   │   ├── SyncReadWrite.cs
│   │   │       │   │   └── sync_read_write.csproj
│   │   │       │   └── sync_read_write.sln
│   │   │       └── win64
│   │   │           ├── sync_read_write
│   │   │           │   ├── App.config
│   │   │           │   ├── dynamixel.cs
│   │   │           │   ├── Properties
│   │   │           │   │   └── AssemblyInfo.cs
│   │   │           │   ├── SyncReadWrite.cs
│   │   │           │   └── sync_read_write.csproj
│   │   │           └── sync_read_write.sln
│   │   └── protocol_combined
│   │       ├── win32
│   │       │   ├── protocol_combined
│   │       │   │   ├── App.config
│   │       │   │   ├── dynamixel.cs
│   │       │   │   ├── obj
│   │       │   │   │   ├── Debug
│   │       │   │   │   │   └── protocol_combined.csproj.CoreCompileInputs.cache
│   │       │   │   │   ├── Release
│   │       │   │   │   │   └── protocol_combined.csproj.CoreCompileInputs.cache
│   │       │   │   │   └── x86
│   │       │   │   │       ├── Debug
│   │       │   │   │       │   └── protocol_combined.csproj.CoreCompileInputs.cache
│   │       │   │   │       └── Release
│   │       │   │   │           └── protocol_combined.csproj.CoreCompileInputs.cache
│   │       │   │   ├── Properties
│   │       │   │   │   └── AssemblyInfo.cs
│   │       │   │   ├── ProtocolCombined.cs
│   │       │   │   └── protocol_combined.csproj
│   │       │   └── protocol_combined.sln
│   │       └── win64
│   │           ├── protocol_combined
│   │           │   ├── App.config
│   │           │   ├── dynamixel.cs
│   │           │   ├── obj
│   │           │   │   ├── Debug
│   │           │   │   │   └── protocol_combined.csproj.CoreCompileInputs.cache
│   │           │   │   ├── Release
│   │           │   │   │   └── protocol_combined.csproj.CoreCompileInputs.cache
│   │           │   │   └── x64
│   │           │   │       ├── Debug
│   │           │   │       │   └── protocol_combined.csproj.CoreCompileInputs.cache
│   │           │   │       └── Release
│   │           │   │           ├── protocol_combined.csprojAssemblyReference.cache
│   │           │   │           ├── protocol_combined.csproj.CoreCompileInputs.cache
│   │           │   │           ├── TemporaryGeneratedFile_036C0B5B-1481-4323-8D20-8F5ADCB23D92.cs
│   │           │   │           ├── TemporaryGeneratedFile_5937a670-0e60-4077-877b-f7221da3dda1.cs
│   │           │   │           └── TemporaryGeneratedFile_E7A71F73-0F8D-4B9B-B56E-8E70B10BC5D3.cs
│   │           │   ├── Properties
│   │           │   │   └── AssemblyInfo.cs
│   │           │   ├── ProtocolCombined.cs
│   │           │   └── protocol_combined.csproj
│   │           └── protocol_combined.sln
│   ├── c++
│   │   ├── build
│   │   │   ├── linux32
│   │   │   │   └── Makefile
│   │   │   ├── linux64
│   │   │   │   └── Makefile
│   │   │   ├── linux_sbc
│   │   │   │   └── Makefile
│   │   │   ├── mac
│   │   │   │   └── Makefile
│   │   │   ├── win32
│   │   │   │   ├── dxl_x86_cpp
│   │   │   │   │   ├── dxl_x86_cpp.vcxproj
│   │   │   │   │   ├── dxl_x86_cpp.vcxproj.filters
│   │   │   │   │   └── dxl_x86_cpp.vcxproj.user
│   │   │   │   ├── dxl_x86_cpp.sln
│   │   │   │   └── output
│   │   │   │       ├── dxl_x86_cpp.dll
│   │   │   │       └── dxl_x86_cpp.lib
│   │   │   └── win64
│   │   │       ├── dxl_x64_cpp
│   │   │       │   ├── dxl_x64_cpp.vcxproj
│   │   │       │   └── dxl_x64_cpp.vcxproj.filters
│   │   │       ├── dxl_x64_cpp.sln
│   │   │       └── output
│   │   │           ├── dxl_x64_cpp.dll
│   │   │           └── dxl_x64_cpp.lib
│   │   ├── example
│   │   │   ├── dxl_monitor
│   │   │   │   ├── dxl_monitor.cpp
│   │   │   │   ├── linux32
│   │   │   │   │   └── Makefile
│   │   │   │   ├── linux64
│   │   │   │   │   └── Makefile
│   │   │   │   ├── linux_sbc
│   │   │   │   │   └── Makefile
│   │   │   │   ├── mac
│   │   │   │   │   └── Makefile
│   │   │   │   ├── win32
│   │   │   │   │   ├── dxl_monitor
│   │   │   │   │   │   ├── dxl_monitor.vcxproj
│   │   │   │   │   │   ├── dxl_monitor.vcxproj.filters
│   │   │   │   │   │   └── dxl_monitor.vcxproj.user
│   │   │   │   │   └── dxl_monitor.sln
│   │   │   │   └── win64
│   │   │   │       ├── dxl_monitor
│   │   │   │       │   ├── dxl_monitor.vcxproj
│   │   │   │       │   ├── dxl_monitor.vcxproj.filters
│   │   │   │       │   └── dxl_monitor.vcxproj.user
│   │   │   │       └── dxl_monitor.sln
│   │   │   ├── protocol1.0
│   │   │   │   ├── bulk_read
│   │   │   │   │   ├── bulk_read.cpp
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── bulk_read
│   │   │   │   │   │   │   ├── bulk_read.vcxproj
│   │   │   │   │   │   │   ├── bulk_read.vcxproj.filters
│   │   │   │   │   │   │   └── bulk_read.vcxproj.user
│   │   │   │   │   │   └── bulk_read.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── bulk_read
│   │   │   │   │       │   ├── bulk_read.vcxproj
│   │   │   │   │       │   ├── bulk_read.vcxproj.filters
│   │   │   │   │       │   └── bulk_read.vcxproj.user
│   │   │   │   │       └── bulk_read.sln
│   │   │   │   ├── multi_port
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── multi_port.cpp
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── multi_port
│   │   │   │   │   │   │   ├── multi_port.vcxproj
│   │   │   │   │   │   │   ├── multi_port.vcxproj.filters
│   │   │   │   │   │   │   └── multi_port.vcxproj.user
│   │   │   │   │   │   └── multi_port.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── multi_port
│   │   │   │   │       │   ├── multi_port.vcxproj
│   │   │   │   │       │   ├── multi_port.vcxproj.filters
│   │   │   │   │       │   └── multi_port.vcxproj.user
│   │   │   │   │       └── multi_port.sln
│   │   │   │   ├── ping
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── ping.cpp
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── ping
│   │   │   │   │   │   │   ├── ping.vcxproj
│   │   │   │   │   │   │   ├── ping.vcxproj.filters
│   │   │   │   │   │   │   └── ping.vcxproj.user
│   │   │   │   │   │   └── ping.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── ping
│   │   │   │   │       │   ├── ping.vcxproj
│   │   │   │   │       │   ├── ping.vcxproj.filters
│   │   │   │   │       │   └── ping.vcxproj.user
│   │   │   │   │       └── ping.sln
│   │   │   │   ├── read_write
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── read_write.cpp
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── read_write
│   │   │   │   │   │   │   ├── read_write.vcxproj
│   │   │   │   │   │   │   ├── read_write.vcxproj.filters
│   │   │   │   │   │   │   └── read_write.vcxproj.user
│   │   │   │   │   │   └── read_write.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── read_write
│   │   │   │   │       │   ├── read_write.vcxproj
│   │   │   │   │       │   ├── read_write.vcxproj.filters
│   │   │   │   │       │   └── read_write.vcxproj.user
│   │   │   │   │       └── read_write.sln
│   │   │   │   ├── reset
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── reset.cpp
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── reset
│   │   │   │   │   │   │   ├── reset.vcxproj
│   │   │   │   │   │   │   ├── reset.vcxproj.filters
│   │   │   │   │   │   │   └── reset.vcxproj.user
│   │   │   │   │   │   └── reset.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── reset
│   │   │   │   │       │   ├── reset.vcxproj
│   │   │   │   │       │   ├── reset.vcxproj.filters
│   │   │   │   │       │   └── reset.vcxproj.user
│   │   │   │   │       └── reset.sln
│   │   │   │   └── sync_write
│   │   │   │       ├── linux32
│   │   │   │       │   └── Makefile
│   │   │   │       ├── linux64
│   │   │   │       │   └── Makefile
│   │   │   │       ├── linux_sbc
│   │   │   │       │   └── Makefile
│   │   │   │       ├── mac
│   │   │   │       │   └── Makefile
│   │   │   │       ├── sync_write.cpp
│   │   │   │       ├── win32
│   │   │   │       │   ├── sync_write
│   │   │   │       │   │   ├── sync_write.vcxproj
│   │   │   │       │   │   ├── sync_write.vcxproj.filters
│   │   │   │       │   │   └── sync_write.vcxproj.user
│   │   │   │       │   └── sync_write.sln
│   │   │   │       └── win64
│   │   │   │           ├── sync_write
│   │   │   │           │   ├── sync_write.vcxproj
│   │   │   │           │   ├── sync_write.vcxproj.filters
│   │   │   │           │   └── sync_write.vcxproj.user
│   │   │   │           └── sync_write.sln
│   │   │   ├── protocol2.0
│   │   │   │   ├── broadcast_ping
│   │   │   │   │   ├── broadcast_ping.cpp
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── broadcast_ping
│   │   │   │   │   │   │   ├── broadcast_ping.vcxproj
│   │   │   │   │   │   │   ├── broadcast_ping.vcxproj.filters
│   │   │   │   │   │   │   └── broadcast_ping.vcxproj.user
│   │   │   │   │   │   └── broadcast_ping.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── broadcast_ping
│   │   │   │   │       │   ├── broadcast_ping.vcxproj
│   │   │   │   │       │   ├── broadcast_ping.vcxproj.filters
│   │   │   │   │       │   └── broadcast_ping.vcxproj.user
│   │   │   │   │       └── broadcast_ping.sln
│   │   │   │   ├── bulk_read_write
│   │   │   │   │   ├── bulk_read_write.cpp
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── bulk_read_write
│   │   │   │   │   │   │   ├── bulk_read_write.vcxproj
│   │   │   │   │   │   │   ├── bulk_read_write.vcxproj.filters
│   │   │   │   │   │   │   └── bulk_read_write.vcxproj.user
│   │   │   │   │   │   └── bulk_read_write.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── bulk_read_write
│   │   │   │   │       │   ├── bulk_read_write.vcxproj
│   │   │   │   │       │   ├── bulk_read_write.vcxproj.filters
│   │   │   │   │       │   └── bulk_read_write.vcxproj.user
│   │   │   │   │       └── bulk_read_write.sln
│   │   │   │   ├── clear_multi_turn
│   │   │   │   │   ├── clear_multi_turn.cpp
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── clear_multi_turn
│   │   │   │   │   │   │   ├── clear_multi_turn.vcxproj
│   │   │   │   │   │   │   ├── clear_multi_turn.vcxproj.filters
│   │   │   │   │   │   │   └── clear_multi_turn.vcxproj.user
│   │   │   │   │   │   └── clear_multi_turn.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── clear_multi_turn
│   │   │   │   │       │   ├── clear_multi_turn.vcxproj
│   │   │   │   │       │   ├── clear_multi_turn.vcxproj.filters
│   │   │   │   │       │   └── clear_multi_turn.vcxproj.user
│   │   │   │   │       └── clear_multi_turn.sln
│   │   │   │   ├── factory_reset
│   │   │   │   │   ├── factory_reset.cpp
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── factory_reset
│   │   │   │   │   │   │   ├── factory_reset.vcxproj
│   │   │   │   │   │   │   ├── factory_reset.vcxproj.filters
│   │   │   │   │   │   │   └── factory_reset.vcxproj.user
│   │   │   │   │   │   └── factory_reset.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── factory_reset
│   │   │   │   │       │   ├── factory_reset.vcxproj
│   │   │   │   │       │   ├── factory_reset.vcxproj.filters
│   │   │   │   │       │   └── factory_reset.vcxproj.user
│   │   │   │   │       └── factory_reset.sln
│   │   │   │   ├── indirect_address
│   │   │   │   │   ├── indirect_address.cpp
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── indirect_address
│   │   │   │   │   │   │   ├── indirect_address.vcxproj
│   │   │   │   │   │   │   ├── indirect_address.vcxproj.filters
│   │   │   │   │   │   │   └── indirect_address.vcxproj.user
│   │   │   │   │   │   └── indirect_address.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── indirect_address
│   │   │   │   │       │   ├── indirect_address.vcxproj
│   │   │   │   │       │   ├── indirect_address.vcxproj.filters
│   │   │   │   │       │   └── indirect_address.vcxproj.user
│   │   │   │   │       └── indirect_address.sln
│   │   │   │   ├── multi_port
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── multi_port.cpp
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── multi_port
│   │   │   │   │   │   │   ├── multi_port.vcxproj
│   │   │   │   │   │   │   ├── multi_port.vcxproj.filters
│   │   │   │   │   │   │   └── multi_port.vcxproj.user
│   │   │   │   │   │   └── multi_port.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── multi_port
│   │   │   │   │       │   ├── multi_port.vcxproj
│   │   │   │   │       │   ├── multi_port.vcxproj.filters
│   │   │   │   │       │   └── multi_port.vcxproj.user
│   │   │   │   │       └── multi_port.sln
│   │   │   │   ├── ping
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── ping.cpp
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── ping
│   │   │   │   │   │   │   ├── ping.vcxproj
│   │   │   │   │   │   │   ├── ping.vcxproj.filters
│   │   │   │   │   │   │   └── ping.vcxproj.user
│   │   │   │   │   │   └── ping.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── ping
│   │   │   │   │       │   ├── ping.vcxproj
│   │   │   │   │       │   ├── ping.vcxproj.filters
│   │   │   │   │       │   └── ping.vcxproj.user
│   │   │   │   │       └── ping.sln
│   │   │   │   ├── read_write
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── read_write.cpp
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── read_write
│   │   │   │   │   │   │   ├── read_write.vcxproj
│   │   │   │   │   │   │   ├── read_write.vcxproj.filters
│   │   │   │   │   │   │   └── read_write.vcxproj.user
│   │   │   │   │   │   └── read_write.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── read_write
│   │   │   │   │       │   ├── read_write.vcxproj
│   │   │   │   │       │   ├── read_write.vcxproj.filters
│   │   │   │   │       │   └── read_write.vcxproj.user
│   │   │   │   │       └── read_write.sln
│   │   │   │   ├── reboot
│   │   │   │   │   ├── linux32
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux64
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── linux_sbc
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── mac
│   │   │   │   │   │   └── Makefile
│   │   │   │   │   ├── reboot.cpp
│   │   │   │   │   ├── win32
│   │   │   │   │   │   ├── reboot
│   │   │   │   │   │   │   ├── reboot.vcxproj
│   │   │   │   │   │   │   ├── reboot.vcxproj.filters
│   │   │   │   │   │   │   └── reboot.vcxproj.user
│   │   │   │   │   │   └── reboot.sln
│   │   │   │   │   └── win64
│   │   │   │   │       ├── reboot
│   │   │   │   │       │   ├── reboot.vcxproj
│   │   │   │   │       │   ├── reboot.vcxproj.filters
│   │   │   │   │       │   └── reboot.vcxproj.user
│   │   │   │   │       └── reboot.sln
│   │   │   │   └── sync_read_write
│   │   │   │       ├── linux32
│   │   │   │       │   └── Makefile
│   │   │   │       ├── linux64
│   │   │   │       │   └── Makefile
│   │   │   │       ├── linux_sbc
│   │   │   │       │   └── Makefile
│   │   │   │       ├── mac
│   │   │   │       │   └── Makefile
│   │   │   │       ├── sync_read_write.cpp
│   │   │   │       ├── win32
│   │   │   │       │   ├── sync_read_write
│   │   │   │       │   │   ├── sync_read_write.vcxproj
│   │   │   │       │   │   ├── sync_read_write.vcxproj.filters
│   │   │   │       │   │   └── sync_read_write.vcxproj.user
│   │   │   │       │   └── sync_read_write.sln
│   │   │   │       └── win64
│   │   │   │           ├── sync_read_write
│   │   │   │           │   ├── sync_read_write.vcxproj
│   │   │   │           │   ├── sync_read_write.vcxproj.filters
│   │   │   │           │   └── sync_read_write.vcxproj.user
│   │   │   │           └── sync_read_write.sln
│   │   │   └── protocol_combined
│   │   │       ├── linux32
│   │   │       │   └── Makefile
│   │   │       ├── linux64
│   │   │       │   └── Makefile
│   │   │       ├── linux_sbc
│   │   │       │   └── Makefile
│   │   │       ├── mac
│   │   │       │   └── Makefile
│   │   │       ├── protocol_combined.cpp
│   │   │       ├── win32
│   │   │       │   ├── protocol_combined
│   │   │       │   │   ├── protocol_combined.vcxproj
│   │   │       │   │   ├── protocol_combined.vcxproj.filters
│   │   │       │   │   └── protocol_combined.vcxproj.user
│   │   │       │   └── protocol_combined.sln
│   │   │       └── win64
│   │   │           ├── protocol_combined
│   │   │           │   ├── protocol_combined.vcxproj
│   │   │           │   ├── protocol_combined.vcxproj.filters
│   │   │           │   └── protocol_combined.vcxproj.user
│   │   │           └── protocol_combined.sln
│   │   ├── include
│   │   │   └── dynamixel_sdk
│   │   │       ├── dynamixel_sdk.h
│   │   │       ├── group_bulk_read.h
│   │   │       ├── group_bulk_write.h
│   │   │       ├── group_sync_read.h
│   │   │       ├── group_sync_write.h
│   │   │       ├── packet_handler.h
│   │   │       ├── port_handler_arduino.h
│   │   │       ├── port_handler.h
│   │   │       ├── port_handler_linux.h
│   │   │       ├── port_handler_mac.h
│   │   │       ├── port_handler_windows.h
│   │   │       ├── protocol1_packet_handler.h
│   │   │       └── protocol2_packet_handler.h
│   │   ├── keywords.txt
│   │   ├── library.properties
│   │   └── src
│   │       ├── dynamixel_sdk
│   │       │   ├── group_bulk_read.cpp
│   │       │   ├── group_bulk_write.cpp
│   │       │   ├── group_sync_read.cpp
│   │       │   ├── group_sync_write.cpp
│   │       │   ├── packet_handler.cpp
│   │       │   ├── port_handler_arduino.cpp
│   │       │   ├── port_handler.cpp
│   │       │   ├── port_handler_linux.cpp
│   │       │   ├── port_handler_mac.cpp
│   │       │   ├── port_handler_windows.cpp
│   │       │   ├── protocol1_packet_handler.cpp
│   │       │   └── protocol2_packet_handler.cpp
│   │       └── DynamixelSDK.h
│   ├── CONTRIBUTING.md
│   ├── documents
│   │   └── cpp
│   │       └── html
│   │           ├── arrowdown.png
│   │           ├── arrowright.png
│   │           ├── bc_s.png
│   │           ├── bdwn.png
│   │           ├── classdynamixel_1_1PacketHandler__inherit__graph.map
│   │           ├── classdynamixel_1_1PacketHandler__inherit__graph.md5
│   │           ├── classdynamixel_1_1PacketHandler__inherit__graph.png
│   │           ├── classdynamixel_1_1PortHandlerArduino__coll__graph.map
│   │           ├── classdynamixel_1_1PortHandlerArduino__coll__graph.md5
│   │           ├── classdynamixel_1_1PortHandlerArduino__coll__graph.png
│   │           ├── classdynamixel_1_1PortHandlerArduino__inherit__graph.map
│   │           ├── classdynamixel_1_1PortHandlerArduino__inherit__graph.md5
│   │           ├── classdynamixel_1_1PortHandlerArduino__inherit__graph.png
│   │           ├── classdynamixel_1_1PortHandler__inherit__graph.map
│   │           ├── classdynamixel_1_1PortHandler__inherit__graph.md5
│   │           ├── classdynamixel_1_1PortHandler__inherit__graph.png
│   │           ├── classdynamixel_1_1PortHandlerLinux__coll__graph.map
│   │           ├── classdynamixel_1_1PortHandlerLinux__coll__graph.md5
│   │           ├── classdynamixel_1_1PortHandlerLinux__coll__graph.png
│   │           ├── classdynamixel_1_1PortHandlerLinux__inherit__graph.map
│   │           ├── classdynamixel_1_1PortHandlerLinux__inherit__graph.md5
│   │           ├── classdynamixel_1_1PortHandlerLinux__inherit__graph.png
│   │           ├── classdynamixel_1_1PortHandlerMac__coll__graph.map
│   │           ├── classdynamixel_1_1PortHandlerMac__coll__graph.md5
│   │           ├── classdynamixel_1_1PortHandlerMac__coll__graph.png
│   │           ├── classdynamixel_1_1PortHandlerMac__inherit__graph.map
│   │           ├── classdynamixel_1_1PortHandlerMac__inherit__graph.md5
│   │           ├── classdynamixel_1_1PortHandlerMac__inherit__graph.png
│   │           ├── classdynamixel_1_1PortHandlerWindows__coll__graph.map
│   │           ├── classdynamixel_1_1PortHandlerWindows__coll__graph.md5
│   │           ├── classdynamixel_1_1PortHandlerWindows__coll__graph.png
│   │           ├── classdynamixel_1_1PortHandlerWindows__inherit__graph.map
│   │           ├── classdynamixel_1_1PortHandlerWindows__inherit__graph.md5
│   │           ├── classdynamixel_1_1PortHandlerWindows__inherit__graph.png
│   │           ├── classdynamixel_1_1Protocol1PacketHandler__coll__graph.map
│   │           ├── classdynamixel_1_1Protocol1PacketHandler__coll__graph.md5
│   │           ├── classdynamixel_1_1Protocol1PacketHandler__coll__graph.png
│   │           ├── classdynamixel_1_1Protocol1PacketHandler__inherit__graph.map
│   │           ├── classdynamixel_1_1Protocol1PacketHandler__inherit__graph.md5
│   │           ├── classdynamixel_1_1Protocol1PacketHandler__inherit__graph.png
│   │           ├── classdynamixel_1_1Protocol2PacketHandler__coll__graph.map
│   │           ├── classdynamixel_1_1Protocol2PacketHandler__coll__graph.md5
│   │           ├── classdynamixel_1_1Protocol2PacketHandler__coll__graph.png
│   │           ├── classdynamixel_1_1Protocol2PacketHandler__inherit__graph.map
│   │           ├── classdynamixel_1_1Protocol2PacketHandler__inherit__graph.md5
│   │           ├── classdynamixel_1_1Protocol2PacketHandler__inherit__graph.png
│   │           ├── closed.png
│   │           ├── doc.png
│   │           ├── doxygen.css
│   │           ├── doxygen.png
│   │           ├── dynsections.js
│   │           ├── folderclosed.png
│   │           ├── folderopen.png
│   │           ├── graph_legend.md5
│   │           ├── graph_legend.png
│   │           ├── inherit_graph_0.map
│   │           ├── inherit_graph_0.md5
│   │           ├── inherit_graph_0.png
│   │           ├── inherit_graph_1.map
│   │           ├── inherit_graph_1.md5
│   │           ├── inherit_graph_1.png
│   │           ├── inherit_graph_2.map
│   │           ├── inherit_graph_2.md5
│   │           ├── inherit_graph_2.png
│   │           ├── inherit_graph_3.map
│   │           ├── inherit_graph_3.md5
│   │           ├── inherit_graph_3.png
│   │           ├── inherit_graph_4.map
│   │           ├── inherit_graph_4.md5
│   │           ├── inherit_graph_4.png
│   │           ├── inherit_graph_5.map
│   │           ├── inherit_graph_5.md5
│   │           ├── inherit_graph_5.png
│   │           ├── jquery.js
│   │           ├── nav_f.png
│   │           ├── nav_g.png
│   │           ├── nav_h.png
│   │           ├── open.png
│   │           ├── search
│   │           │   ├── all_0.js
│   │           │   ├── all_1.js
│   │           │   ├── all_2.js
│   │           │   ├── all_3.js
│   │           │   ├── all_4.js
│   │           │   ├── all_5.js
│   │           │   ├── all_6.js
│   │           │   ├── all_7.js
│   │           │   ├── all_8.js
│   │           │   ├── all_9.js
│   │           │   ├── all_a.js
│   │           │   ├── all_b.js
│   │           │   ├── all_c.js
│   │           │   ├── all_d.js
│   │           │   ├── classes_0.js
│   │           │   ├── classes_1.js
│   │           │   ├── close.png
│   │           │   ├── functions_0.js
│   │           │   ├── functions_1.js
│   │           │   ├── functions_2.js
│   │           │   ├── functions_3.js
│   │           │   ├── functions_4.js
│   │           │   ├── functions_5.js
│   │           │   ├── functions_6.js
│   │           │   ├── functions_7.js
│   │           │   ├── functions_8.js
│   │           │   ├── functions_9.js
│   │           │   ├── functions_a.js
│   │           │   ├── functions_b.js
│   │           │   ├── functions_c.js
│   │           │   ├── mag_sel.png
│   │           │   ├── pages_0.js
│   │           │   ├── search.css
│   │           │   ├── searchdata.js
│   │           │   ├── search.js
│   │           │   ├── search_l.png
│   │           │   ├── search_m.png
│   │           │   ├── search_r.png
│   │           │   ├── variables_0.js
│   │           │   └── variables_1.js
│   │           ├── splitbar.png
│   │           ├── sync_off.png
│   │           ├── sync_on.png
│   │           ├── tab_a.png
│   │           ├── tab_b.png
│   │           ├── tab_h.png
│   │           ├── tabs.css
│   │           └── tab_s.png
│   ├── Doxyfile
│   ├── java
│   │   ├── dynamixel_functions_java
│   │   │   ├── mac_x64
│   │   │   │   └── Dynamixel.java
│   │   │   ├── x64
│   │   │   │   └── Dynamixel.java
│   │   │   └── x86
│   │   │       └── Dynamixel.java
│   │   ├── protocol1.0
│   │   │   ├── bulk_read
│   │   │   │   └── BulkRead.java
│   │   │   ├── multi_port
│   │   │   │   └── MultiPort.java
│   │   │   ├── ping
│   │   │   │   └── Ping.java
│   │   │   ├── read_write
│   │   │   │   └── ReadWrite.java
│   │   │   ├── reset
│   │   │   │   └── Reset.java
│   │   │   └── sync_write
│   │   │       └── SyncWrite.java
│   │   ├── protocol2.0
│   │   │   ├── broadcast_ping
│   │   │   │   └── BroadcastPing.java
│   │   │   ├── bulk_read_write
│   │   │   │   └── BulkReadWrite.java
│   │   │   ├── clear_multi_turn
│   │   │   │   └── ClearMultiTurn.java
│   │   │   ├── factory_reset
│   │   │   │   └── FactoryReset.java
│   │   │   ├── indirect_address
│   │   │   │   └── IndirectAddress.java
│   │   │   ├── multi_port
│   │   │   │   └── MultiPort.java
│   │   │   ├── ping
│   │   │   │   └── Ping.java
│   │   │   ├── read_write
│   │   │   │   └── ReadWrite.java
│   │   │   ├── reboot
│   │   │   │   └── Reboot.java
│   │   │   └── sync_read_write
│   │   │       └── SyncReadWrite.java
│   │   └── protocol_combined
│   │       └── ProtocolCombined.java
│   ├── labview
│   │   ├── dxl_x86_c.lvlib
│   │   │   ├── dir.mnu
│   │   │   ├── dxl_x86_c.dll
│   │   │   ├── dxl_x86_c.lvlib
│   │   │   └── VIs
│   │   │       ├── bulk Read Tx.vi
│   │   │       ├── bulk Write Tx Only.vi
│   │   │       ├── clear Port.vi
│   │   │       ├── close Port.vi
│   │   │       ├── dir.mnu
│   │   │       ├── factory Reset.vi
│   │   │       ├── get Baud Rate.vi
│   │   │       ├── get Broadcast Ping Result.vi
│   │   │       ├── get Last Rx Packet Error.vi
│   │   │       ├── get Last Tx Rx Result.vi
│   │   │       ├── get Port Name.vi
│   │   │       ├── get Rx Packet Error.vi
│   │   │       ├── get Tx Rx Result.vi
│   │   │       ├── group Bulk Read Add Param.vi
│   │   │       ├── group Bulk Read Clear Param.vi
│   │   │       ├── group Bulk Read Get Data.vi
│   │   │       ├── group Bulk Read Is Available.vi
│   │   │       ├── group Bulk Read Remove Param.vi
│   │   │       ├── group Bulk Read Rx Packet.vi
│   │   │       ├── group Bulk Read Tx Packet.vi
│   │   │       ├── group Bulk Read Tx Rx Packet.vi
│   │   │       ├── group Bulk Read.vi
│   │   │       ├── group Bulk Write Add Param.vi
│   │   │       ├── group Bulk Write Change Param.vi
│   │   │       ├── group Bulk Write Clear Param.vi
│   │   │       ├── group Bulk Write Remove Param.vi
│   │   │       ├── group Bulk Write Tx Packet.vi
│   │   │       ├── group Bulk Write.vi
│   │   │       ├── group Sync Read Add Param.vi
│   │   │       ├── group Sync Read Clear Param.vi
│   │   │       ├── group Sync Read Get Data.vi
│   │   │       ├── group Sync Read Is Available.vi
│   │   │       ├── group Sync Read Remove Param.vi
│   │   │       ├── group Sync Read Rx Packet.vi
│   │   │       ├── group Sync Read Tx Packet.vi
│   │   │       ├── group Sync Read Tx Rx Packet.vi
│   │   │       ├── group Sync Read.vi
│   │   │       ├── group Sync Write Add Param.vi
│   │   │       ├── group Sync Write Change Param.vi
│   │   │       ├── group Sync Write Clear Param.vi
│   │   │       ├── group Sync Write Remove Param.vi
│   │   │       ├── group Sync Write Tx Packet.vi
│   │   │       ├── group Sync Write.vi
│   │   │       ├── is Packet Timeout.vi
│   │   │       ├── open Port.vi
│   │   │       ├── packet Handler.vi
│   │   │       ├── ping Get Model Num.vi
│   │   │       ├── ping.vi
│   │   │       ├── port Handler.vi
│   │   │       ├── print Rx Packet Error.vi
│   │   │       ├── print Tx Rx Result.vi
│   │   │       ├── read1Byte Rx.vi
│   │   │       ├── read1Byte Tx Rx.vi
│   │   │       ├── read1Byte Tx.vi
│   │   │       ├── read2Byte Rx.vi
│   │   │       ├── read2Byte Tx Rx.vi
│   │   │       ├── read2Byte Tx.vi
│   │   │       ├── read4Byte Rx.vi
│   │   │       ├── read4Byte Tx Rx.vi
│   │   │       ├── read4Byte Tx.vi
│   │   │       ├── read Port.vi
│   │   │       ├── read Rx.vi
│   │   │       ├── read Tx Rx.vi
│   │   │       ├── read Tx.vi
│   │   │       ├── reboot.vi
│   │   │       ├── reg Write Tx Only.vi
│   │   │       ├── reg Write Tx Rx.vi
│   │   │       ├── rx Packet.vi
│   │   │       ├── set Baud Rate.vi
│   │   │       ├── set Data Write.vi
│   │   │       ├── set Packet Timeout M Sec.vi
│   │   │       ├── set Packet Timeout.vi
│   │   │       ├── set Port Name.vi
│   │   │       ├── sync Read Tx.vi
│   │   │       ├── sync Write Tx Only.vi
│   │   │       ├── tx Packet.vi
│   │   │       ├── tx Rx Packet.vi
│   │   │       ├── write1Byte Tx Only.vi
│   │   │       ├── write1Byte Tx Rx.vi
│   │   │       ├── write2Byte Tx Only.vi
│   │   │       ├── write2Byte Tx Rx.vi
│   │   │       ├── write4Byte Tx Only.vi
│   │   │       ├── write4Byte Tx Rx.vi
│   │   │       ├── write Port.vi
│   │   │       ├── write Tx Only.vi
│   │   │       └── write Tx Rx.vi
│   │   ├── protocol1.0
│   │   │   ├── bulk_read.vi
│   │   │   ├── factory_reset.vi
│   │   │   ├── multi_port.vi
│   │   │   ├── ping.vi
│   │   │   ├── read_write.vi
│   │   │   └── sync_write.vi
│   │   ├── protocol2.0
│   │   │   ├── broadcast_ping.vi
│   │   │   ├── bulk_read_write.vi
│   │   │   ├── clear_multi_turn.vi
│   │   │   ├── factory_reset.vi
│   │   │   ├── indirect_address.vi
│   │   │   ├── multi_port.vi
│   │   │   ├── ping.vi
│   │   │   ├── read_write_p.vi
│   │   │   ├── read_write_x.vi
│   │   │   ├── reboot.vi
│   │   │   └── sync_read_write.vi
│   │   └── protocol_combined
│   │       └── protocol_combined.vi
│   ├── LICENSE
│   ├── matlab
│   │   ├── m_basic_function
│   │   │   ├── group_bulk_read
│   │   │   │   ├── groupBulkReadAddParam.m
│   │   │   │   ├── groupBulkReadClearParam.m
│   │   │   │   ├── groupBulkReadGetData.m
│   │   │   │   ├── groupBulkReadIsAvailable.m
│   │   │   │   ├── groupBulkRead.m
│   │   │   │   ├── groupBulkReadRemoveParam.m
│   │   │   │   ├── groupBulkReadRxPacket.m
│   │   │   │   ├── groupBulkReadTxPacket.m
│   │   │   │   └── groupBulkReadTxRxPacket.m
│   │   │   ├── group_bulk_write
│   │   │   │   ├── groupBulkWriteAddParam.m
│   │   │   │   ├── groupBulkWriteChangeParam.m
│   │   │   │   ├── groupBulkWriteClearParam.m
│   │   │   │   ├── groupBulkWrite.m
│   │   │   │   ├── groupBulkWriteRemoveParam.m
│   │   │   │   └── groupBulkWriteTxPacket.m
│   │   │   ├── group_sync_read
│   │   │   │   ├── groupSyncReadAddParam.m
│   │   │   │   ├── groupSyncReadClearParam.m
│   │   │   │   ├── groupSyncReadGetData.m
│   │   │   │   ├── groupSyncReadIsAvailable.m
│   │   │   │   ├── groupSyncRead.m
│   │   │   │   ├── groupSyncReadRemoveParam.m
│   │   │   │   ├── groupSyncReadRxPacket.m
│   │   │   │   ├── groupSyncReadTxPacket.m
│   │   │   │   └── groupSyncReadTxRxPacket.m
│   │   │   ├── group_sync_write
│   │   │   │   ├── groupSyncWriteAddParam.m
│   │   │   │   ├── groupSyncWriteChangeParam.m
│   │   │   │   ├── groupSyncWriteClearParam.m
│   │   │   │   ├── groupSyncWrite.m
│   │   │   │   ├── groupSyncWriteRemoveParam.m
│   │   │   │   └── groupSyncWriteTxPacket.m
│   │   │   ├── packet_handler
│   │   │   │   ├── broadcastPing.m
│   │   │   │   ├── bulkReadTx.m
│   │   │   │   ├── bulkWriteTxOnly.m
│   │   │   │   ├── clearMultiTurn.m
│   │   │   │   ├── factoryReset.m
│   │   │   │   ├── getBroadcastPingResult.m
│   │   │   │   ├── getDataRead.m
│   │   │   │   ├── getLastRxPacketError.m
│   │   │   │   ├── getLastTxRxResult.m
│   │   │   │   ├── getRxPacketError.m
│   │   │   │   ├── getTxRxResult.m
│   │   │   │   ├── packetHandler.m
│   │   │   │   ├── pingGetModelNum.m
│   │   │   │   ├── ping.m
│   │   │   │   ├── read1ByteRx.m
│   │   │   │   ├── read1ByteTx.m
│   │   │   │   ├── read1ByteTxRx.m
│   │   │   │   ├── read2ByteRx.m
│   │   │   │   ├── read2ByteTx.m
│   │   │   │   ├── read2ByteTxRx.m
│   │   │   │   ├── read4ByteRx.m
│   │   │   │   ├── read4ByteTx.m
│   │   │   │   ├── read4ByteTxRx.m
│   │   │   │   ├── readRx.m
│   │   │   │   ├── readTx.m
│   │   │   │   ├── readTxRx.m
│   │   │   │   ├── reboot.m
│   │   │   │   ├── regWriteTxOnly.m
│   │   │   │   ├── regWriteTxRx.m
│   │   │   │   ├── rxPacket.m
│   │   │   │   ├── setDataWrite.m
│   │   │   │   ├── syncReadTx.m
│   │   │   │   ├── syncWriteTxOnly.m
│   │   │   │   ├── txPacket.m
│   │   │   │   ├── txrxPacket.m
│   │   │   │   ├── write1ByteTxOnly.m
│   │   │   │   ├── write1ByteTxRx.m
│   │   │   │   ├── write2ByteTxOnly.m
│   │   │   │   ├── write2ByteTxRx.m
│   │   │   │   ├── write4ByteTxOnly.m
│   │   │   │   ├── write4ByteTxRx.m
│   │   │   │   ├── writeTxOnly.m
│   │   │   │   └── writeTxRx.m
│   │   │   └── port_handler
│   │   │       ├── clearPort.m
│   │   │       ├── closePort.m
│   │   │       ├── getBaudRate.m
│   │   │       ├── getPortName.m
│   │   │       ├── isPacketTimeout.m
│   │   │       ├── openPort.m
│   │   │       ├── portHandler.m
│   │   │       ├── setBaudRate.m
│   │   │       ├── setPacketTimeout.m
│   │   │       ├── setPacketTimeoutMSec.m
│   │   │       └── setPortName.m
│   │   ├── protocol1.0
│   │   │   ├── bulk_read.m
│   │   │   ├── factory_reset.m
│   │   │   ├── multi_port.m
│   │   │   ├── ping.m
│   │   │   ├── read_write.m
│   │   │   └── sync_write.m
│   │   ├── protocol2.0
│   │   │   ├── broadcast_ping.m
│   │   │   ├── bulk_read_write.m
│   │   │   ├── clear_multi_turn.m
│   │   │   ├── factory_reset.m
│   │   │   ├── indirect_address.m
│   │   │   ├── multi_port.m
│   │   │   ├── ping.m
│   │   │   ├── read_write.m
│   │   │   ├── rebooting.m
│   │   │   └── sync_read_write.m
│   │   └── protocol_combined
│   │       └── protocol_combined.m
│   ├── python
│   │   ├── CATKIN_IGNORE
│   │   ├── LICENSE.txt
│   │   ├── README.txt
│   │   ├── setup.py
│   │   ├── src
│   │   │   └── dynamixel_sdk
│   │   │       ├── group_bulk_read.py
│   │   │       ├── group_bulk_write.py
│   │   │       ├── group_sync_read.py
│   │   │       ├── group_sync_write.py
│   │   │       ├── __init__.py
│   │   │       ├── packet_handler.py
│   │   │       ├── port_handler.py
│   │   │       ├── protocol1_packet_handler.py
│   │   │       ├── protocol2_packet_handler.py
│   │   │       └── robotis_def.py
│   │   └── tests
│   │       ├── protocol1_0
│   │       │   ├── bulk_read.py
│   │       │   ├── factory_reset.py
│   │       │   ├── multi_port.py
│   │       │   ├── ping.py
│   │       │   ├── read_write.py
│   │       │   └── sync_write.py
│   │       ├── protocol2_0
│   │       │   ├── broadcast_ping.py
│   │       │   ├── bulk_read_write.py
│   │       │   ├── clear_multi_turn.py
│   │       │   ├── factory_reset.py
│   │       │   ├── indirect_address.py
│   │       │   ├── multi_port.py
│   │       │   ├── ping.py
│   │       │   ├── read_write.py
│   │       │   ├── reboot.py
│   │       │   └── sync_read_write.py
│   │       └── protocol_combined.py
│   ├── README.md
│   ├── ReleaseNote.md
│   └── ros
│       ├── dynamixel_sdk
│       │   ├── CHANGELOG.rst
│       │   ├── CMakeLists.txt
│       │   ├── include
│       │   │   └── dynamixel_sdk
│       │   │       ├── dynamixel_sdk.h
│       │   │       ├── group_bulk_read.h
│       │   │       ├── group_bulk_write.h
│       │   │       ├── group_sync_read.h
│       │   │       ├── group_sync_write.h
│       │   │       ├── packet_handler.h
│       │   │       ├── port_handler_arduino.h
│       │   │       ├── port_handler.h
│       │   │       ├── port_handler_linux.h
│       │   │       ├── port_handler_mac.h
│       │   │       ├── port_handler_windows.h
│       │   │       ├── protocol1_packet_handler.h
│       │   │       └── protocol2_packet_handler.h
│       │   ├── package.xml
│       │   ├── setup.py
│       │   └── src
│       │       ├── dynamixel_sdk
│       │       │   ├── group_bulk_read.cpp
│       │       │   ├── group_bulk_read.py
│       │       │   ├── group_bulk_write.cpp
│       │       │   ├── group_bulk_write.py
│       │       │   ├── group_sync_read.cpp
│       │       │   ├── group_sync_read.py
│       │       │   ├── group_sync_write.cpp
│       │       │   ├── group_sync_write.py
│       │       │   ├── __init__.py
│       │       │   ├── packet_handler.cpp
│       │       │   ├── packet_handler.py
│       │       │   ├── port_handler_arduino.cpp
│       │       │   ├── port_handler.cpp
│       │       │   ├── port_handler_linux.cpp
│       │       │   ├── port_handler_mac.cpp
│       │       │   ├── port_handler.py
│       │       │   ├── port_handler_windows.cpp
│       │       │   ├── protocol1_packet_handler.cpp
│       │       │   ├── protocol1_packet_handler.py
│       │       │   ├── protocol2_packet_handler.cpp
│       │       │   ├── protocol2_packet_handler.py
│       │       │   └── robotis_def.py
│       │       └── DynamixelSDK.h
│       └── dynamixel_sdk_examples
│           ├── CHANGELOG.rst
│           ├── CMakeLists.txt
│           ├── msg
│           │   ├── BulkSetItem.msg
│           │   ├── SetPosition.msg
│           │   └── SyncSetPosition.msg
│           ├── package.xml
│           ├── src
│           │   ├── bulk_read_write_node.cpp
│           │   ├── indirect_address_node.cpp
│           │   ├── read_write_node.cpp
│           │   ├── read_write_node.py
│           │   └── sync_read_write_node.cpp
│           └── srv
│               ├── BulkGetItem.srv
│               ├── GetPosition.srv
│               └── SyncGetPosition.srv
├── fiducial_msgs
│   ├── CHANGELOG.rst
│   ├── CMakeLists.txt
│   ├── msg
│   │   ├── FiducialArray.msg
│   │   ├── FiducialMapEntryArray.msg
│   │   ├── FiducialMapEntry.msg
│   │   ├── Fiducial.msg
│   │   ├── FiducialTransformArray.msg
│   │   └── FiducialTransform.msg
│   ├── package.xml
│   └── srv
│       └── InitializeMap.srv
├── ld08_driver
│   ├── CMakeLists.txt
│   ├── CONTRIBUTING.md
│   ├── include
│   │   ├── cmd_interface_linux.h
│   │   ├── lipkg.h
│   │   ├── pointdata.h
│   │   ├── slbf.h
│   │   └── transform.h
│   ├── launch
│   │   └── ld08.launch
│   ├── LICENSE
│   ├── package.xml
│   ├── README.md
│   ├── rviz
│   │   └── ldlidar.rviz
│   └── src
│       ├── cmd_interface_linux.cpp
│       ├── ld08_driver.cpp
│       ├── lipkg.cpp
│       ├── slbf.cpp
│       └── transform.cpp
├── raspicam_node
│   ├── camera_info
│   │   ├── camerav1_1280x720.yaml
│   │   ├── camerav2_1280x720.yaml
│   │   ├── camerav2_1280x960.yaml
│   │   ├── camerav2_1640x1232.yaml
│   │   └── camerav2_410x308.yaml
│   ├── cfg
│   │   └── Camera.cfg
│   ├── CHANGELOG.rst
│   ├── CMakeLists.txt
│   ├── include
│   │   ├── mmal_cxx_helper.h
│   │   └── RaspiCamControl.h
│   ├── launch
│   │   ├── camerav1_1280x720.launch
│   │   ├── camerav2_1280x720.launch
│   │   ├── camerav2_1280x960_10fps.launch
│   │   ├── camerav2_1280x960.launch
│   │   ├── camerav2_1640x1232_10fps.launch
│   │   └── camerav2_410x308_30fps.launch
│   ├── LICENSE
│   ├── msg
│   │   └── MotionVectors.msg
│   ├── package.xml
│   ├── README.md
│   ├── reconfigure_raspicam_node.png
│   ├── src
│   │   ├── RaspiCamControl.cpp
│   │   └── raspicam_node.cpp
│   ├── tools
│   │   └── imv_view.py
│   └── vc_hack
│       ├── bcm_host.c
│       ├── Makefile
│       ├── mmal.c
│       ├── mmal_core.c
│       ├── mmal_util.c
│       ├── mmal_vc_client.c
│       ├── vc_client.c
│       ├── vchostif.c
│       └── vcos.c
├── README.md
├── readme.txt
├── tree.txt
├── turtlebot3
│   ├── ISSUE_TEMPLATE.md
│   ├── LICENSE
│   ├── README.md
│   ├── turtlebot3
│   │   ├── CHANGELOG.rst
│   │   ├── CMakeLists.txt
│   │   └── package.xml
│   ├── turtlebot3_bringup
│   │   ├── 99-turtlebot3-cdc.rules
│   │   ├── camera_info
│   │   │   └── turtlebot3_rpicamera.yaml
│   │   ├── CHANGELOG.rst
│   │   ├── CMakeLists.txt
│   │   ├── launch
│   │   │   ├── includes
│   │   │   │   └── description.launch.xml
│   │   │   ├── turtlebot3_core.launch
│   │   │   ├── turtlebot3_lidar.launch
│   │   │   ├── turtlebot3_model.launch
│   │   │   ├── turtlebot3_realsense.launch
│   │   │   ├── turtlebot3_remote.launch
│   │   │   ├── turtlebot3_robot.launch
│   │   │   └── turtlebot3_rpicamera.launch
│   │   ├── package.xml
│   │   ├── scripts
│   │   │   └── create_udev_rules
│   │   └── src
│   │       └── turtlebot3_diagnostics.cpp
│   ├── turtlebot3_description
│   │   ├── CHANGELOG.rst
│   │   ├── CMakeLists.txt
│   │   ├── meshes
│   │   │   ├── bases
│   │   │   │   ├── burger_base.stl
│   │   │   │   ├── waffle_base_for_open_manipulator.stl
│   │   │   │   ├── waffle_base.stl
│   │   │   │   ├── waffle_pi_base_for_open_manipulator.stl
│   │   │   │   └── waffle_pi_base.stl
│   │   │   ├── sensors
│   │   │   │   ├── astra.dae
│   │   │   │   ├── astra.jpg
│   │   │   │   ├── lds.stl
│   │   │   │   ├── r200.dae
│   │   │   │   └── r200.jpg
│   │   │   └── wheels
│   │   │       ├── left_tire.stl
│   │   │       └── right_tire.stl
│   │   ├── package.xml
│   │   ├── rviz
│   │   │   └── model.rviz
│   │   └── urdf
│   │       ├── common_properties.xacro
│   │       ├── turtlebot3_burger_for_autorace_2020.gazebo.xacro
│   │       ├── turtlebot3_burger_for_autorace_2020.urdf.xacro
│   │       ├── turtlebot3_burger_for_autorace.gazebo.xacro
│   │       ├── turtlebot3_burger_for_autorace.urdf.xacro
│   │       ├── turtlebot3_burger.gazebo.xacro
│   │       ├── turtlebot3_burger.urdf.xacro
│   │       ├── turtlebot3_waffle_for_open_manipulator.urdf.xacro
│   │       ├── turtlebot3_waffle.gazebo.xacro
│   │       ├── turtlebot3_waffle_pi_for_open_manipulator.gazebo.xacro
│   │       ├── turtlebot3_waffle_pi_for_open_manipulator.urdf.xacro
│   │       ├── turtlebot3_waffle_pi.gazebo.xacro
│   │       ├── turtlebot3_waffle_pi.urdf.xacro
│   │       └── turtlebot3_waffle.urdf.xacro
│   ├── turtlebot3_example
│   │   ├── action
│   │   │   └── Turtlebot3.action
│   │   ├── CHANGELOG.rst
│   │   ├── CMakeLists.txt
│   │   ├── launch
│   │   │   ├── interactive_markers.launch
│   │   │   ├── turtlebot3_bumper.launch
│   │   │   ├── turtlebot3_client.launch
│   │   │   ├── turtlebot3_cliff.launch
│   │   │   ├── turtlebot3_illumination.launch
│   │   │   ├── turtlebot3_obstacle.launch
│   │   │   ├── turtlebot3_pointop_key.launch
│   │   │   └── turtlebot3_sonar.launch
│   │   ├── nodes
│   │   │   ├── turtlebot3_bumper
│   │   │   ├── turtlebot3_client
│   │   │   ├── turtlebot3_cliff
│   │   │   ├── turtlebot3_illumination
│   │   │   ├── turtlebot3_marker_server
│   │   │   ├── turtlebot3_obstacle
│   │   │   ├── turtlebot3_pointop_key
│   │   │   ├── turtlebot3_server
│   │   │   └── turtlebot3_sonar
│   │   ├── package.xml
│   │   ├── rviz
│   │   │   └── turtlebot3_interactive.rviz
│   │   ├── setup.py
│   │   └── src
│   │       └── turtlebot3_example
│   │           └── __init__.py
│   ├── turtlebot3_navigation
│   │   ├── CHANGELOG.rst
│   │   ├── CMakeLists.txt
│   │   ├── launch
│   │   │   ├── amcl.launch
│   │   │   ├── move_base.launch
│   │   │   └── turtlebot3_navigation.launch
│   │   ├── maps
│   │   │   ├── map.pgm
│   │   │   └── map.yaml
│   │   ├── package.xml
│   │   ├── param
│   │   │   ├── base_local_planner_params.yaml
│   │   │   ├── costmap_common_params_burger.yaml
│   │   │   ├── costmap_common_params_waffle_pi.yaml
│   │   │   ├── costmap_common_params_waffle.yaml
│   │   │   ├── dwa_local_planner_params_burger.yaml
│   │   │   ├── dwa_local_planner_params_waffle_pi.yaml
│   │   │   ├── dwa_local_planner_params_waffle.yaml
│   │   │   ├── global_costmap_params.yaml
│   │   │   ├── local_costmap_params.yaml
│   │   │   └── move_base_params.yaml
│   │   └── rviz
│   │       └── turtlebot3_navigation.rviz
│   ├── turtlebot3_slam
│   │   ├── bag
│   │   │   └── bag_files.md
│   │   ├── CHANGELOG.rst
│   │   ├── CMakeLists.txt
│   │   ├── config
│   │   │   ├── frontier_exploration.yaml
│   │   │   ├── gmapping_params.yaml
│   │   │   ├── karto_mapper_params.yaml
│   │   │   ├── turtlebot3_lds_2d_gazebo.lua
│   │   │   └── turtlebot3_lds_2d.lua
│   │   ├── include
│   │   │   └── turtlebot3_slam
│   │   │       └── flat_world_imu_node.h
│   │   ├── launch
│   │   │   ├── turtlebot3_cartographer.launch
│   │   │   ├── turtlebot3_frontier_exploration.launch
│   │   │   ├── turtlebot3_gmapping.launch
│   │   │   ├── turtlebot3_hector.launch
│   │   │   ├── turtlebot3_karto.launch
│   │   │   ├── turtlebot3_manipulation_slam.launch
│   │   │   └── turtlebot3_slam.launch
│   │   ├── package.xml
│   │   ├── rviz
│   │   │   ├── turtlebot3_cartographer.rviz
│   │   │   ├── turtlebot3_frontier_exploration.rviz
│   │   │   ├── turtlebot3_gmapping.rviz
│   │   │   ├── turtlebot3_hector.rviz
│   │   │   └── turtlebot3_karto.rviz
│   │   └── src
│   │       └── flat_world_imu_node.cpp
│   └── turtlebot3_teleop
│       ├── CHANGELOG.rst
│       ├── CMakeLists.txt
│       ├── launch
│       │   └── turtlebot3_teleop_key.launch
│       ├── nodes
│       │   └── turtlebot3_teleop_key
│       ├── package.xml
│       ├── setup.py
│       └── src
│           └── turtlebot3_teleop
│               └── __init__.py
├── turtlebot3_msgs
│   ├── CHANGELOG.rst
│   ├── CMakeLists.txt
│   ├── LICENSE
│   ├── msg
│   │   ├── SensorState.msg
│   │   ├── Sound.msg
│   │   └── VersionInfo.msg
│   ├── package.xml
│   └── README.md
├── turtlebot3_simulations
│   ├── LICENSE
│   ├── README.md
│   ├── turtlebot3_fake
│   │   ├── CHANGELOG.rst
│   │   ├── CMakeLists.txt
│   │   ├── include
│   │   │   └── turtlebot3_fake
│   │   │       └── turtlebot3_fake.h
│   │   ├── launch
│   │   │   └── turtlebot3_fake.launch
│   │   ├── package.xml
│   │   ├── rviz
│   │   │   └── turtlebot3_fake.rviz
│   │   └── src
│   │       └── turtlebot3_fake.cpp
│   ├── turtlebot3_gazebo
│   │   ├── CHANGELOG.rst
│   │   ├── CMakeLists.txt
│   │   ├── include
│   │   │   └── turtlebot3_gazebo
│   │   │       └── turtlebot3_drive.h
│   │   ├── launch
│   │   │   ├── multi_map_merge.launch
│   │   │   ├── multi_turtlebot3.launch
│   │   │   ├── multi_turtlebot3_slam.launch
│   │   │   ├── turtlebot3_autorace_2020.launch
│   │   │   ├── turtlebot3_autorace.launch
│   │   │   ├── turtlebot3_autorace_mission.launch
│   │   │   ├── turtlebot3_empty_world.launch
│   │   │   ├── turtlebot3_gazebo_rviz.launch
│   │   │   ├── turtlebot3_house.launch
│   │   │   ├── turtlebot3_simulation.launch
│   │   │   ├── turtlebot3_stage_1.launch
│   │   │   ├── turtlebot3_stage_2.launch
│   │   │   ├── turtlebot3_stage_3.launch
│   │   │   ├── turtlebot3_stage_4.launch
│   │   │   └── turtlebot3_world.launch
│   │   ├── models
│   │   │   ├── turtlebot3_autorace
│   │   │   │   ├── course
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── course.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       └── course.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_bar_down
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_bar.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       └── traffic_bar.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_bar_up
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_bar.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       └── traffic_bar.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_light_green
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_light_red
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_light_yellow
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_parking
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_parking.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       └── traffic_parking.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_stop
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_stop.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       └── traffic_stop.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   └── traffic_tunnel
│   │   │   │       ├── materials
│   │   │   │       │   ├── scripts
│   │   │   │       │   │   └── tunnel.material
│   │   │   │       │   └── textures
│   │   │   │       │       └── tunnel.png
│   │   │   │       ├── model.config
│   │   │   │       └── model.sdf
│   │   │   ├── turtlebot3_autorace_2020
│   │   │   │   ├── checker
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── checker.png
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── checker.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       └── checker.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── course
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── course.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       └── course.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_bar_down
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_bar_down.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       └── traffic_bar_down.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_bar_up
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_bar_up.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       └── traffic_bar_up.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_construction
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_construction.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       ├── traffic_construction.png
│   │   │   │   │   │       └── traffic_construction_white_background.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_intersection
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_intersection.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       ├── traffic_intersection.png
│   │   │   │   │   │       └── traffic_intersection_white_background.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_left
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_is_left.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       ├── traffic_left.png
│   │   │   │   │   │       └── traffic_left_white_background.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_light_green
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_light_green.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       └── traffic_light_green.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_light_red
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_light_red.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       ├── traffic_light.png
│   │   │   │   │   │       └── traffic_light_red.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_light_yellow
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_light_yellow.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       └── traffic_light_yellow.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_noentry
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_noentry.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       ├── traffic_noentry.png
│   │   │   │   │   │       └── traffic_noentry_white_background.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_parking
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_parking.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       ├── traffic_parking.png
│   │   │   │   │   │       └── traffic_parking_white_background.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_pl_left
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_pl_left.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       ├── traffic_pl_left.png
│   │   │   │   │   │       └── traffic_pl_left_white_background.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_right
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_right.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       ├── traffic_right.png
│   │   │   │   │   │       └── traffic_right_white_background.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── traffic_stop
│   │   │   │   │   ├── materials
│   │   │   │   │   │   ├── scripts
│   │   │   │   │   │   │   └── traffic_stop.material
│   │   │   │   │   │   └── textures
│   │   │   │   │   │       ├── traffic_stop.png
│   │   │   │   │   │       └── traffic_stop_white_background.png
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   └── traffic_tunnel
│   │   │   │       ├── materials
│   │   │   │       │   ├── scripts
│   │   │   │       │   │   └── tunnel.material
│   │   │   │       │   └── textures
│   │   │   │       │       ├── tunnel.png
│   │   │   │       │       └── tunnel_white_background.png
│   │   │   │       ├── model.config
│   │   │   │       └── model.sdf
│   │   │   ├── turtlebot3_burger
│   │   │   │   ├── model-1_4.sdf
│   │   │   │   ├── model.config
│   │   │   │   └── model.sdf
│   │   │   ├── turtlebot3_common_meshes
│   │   │   │   ├── burger_base.dae
│   │   │   │   ├── lds.dae
│   │   │   │   ├── r200.dae
│   │   │   │   ├── tire.dae
│   │   │   │   ├── waffle_base.dae
│   │   │   │   └── waffle_pi_base.dae
│   │   │   ├── turtlebot3_house
│   │   │   │   ├── model.config
│   │   │   │   └── model.sdf
│   │   │   ├── turtlebot3_plaza
│   │   │   │   ├── goal_box
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── model.config
│   │   │   │   └── model.sdf
│   │   │   ├── turtlebot3_square
│   │   │   │   ├── goal_box
│   │   │   │   │   ├── model.config
│   │   │   │   │   └── model.sdf
│   │   │   │   ├── model.config
│   │   │   │   └── model.sdf
│   │   │   ├── turtlebot3_waffle
│   │   │   │   ├── model-1_4.sdf
│   │   │   │   ├── model.config
│   │   │   │   └── model.sdf
│   │   │   ├── turtlebot3_waffle_pi
│   │   │   │   ├── model-1_4.sdf
│   │   │   │   ├── model.config
│   │   │   │   └── model.sdf
│   │   │   └── turtlebot3_world
│   │   │       ├── meshes
│   │   │       │   ├── hexagon.dae
│   │   │       │   └── wall.dae
│   │   │       ├── model-1_4.sdf
│   │   │       ├── model.config
│   │   │       └── model.sdf
│   │   ├── package.xml
│   │   ├── rviz
│   │   │   ├── multi_turtlebot3_slam.rviz
│   │   │   └── turtlebot3_gazebo_model.rviz
│   │   ├── src
│   │   │   └── turtlebot3_drive.cpp
│   │   └── worlds
│   │       ├── empty.world
│   │       ├── turtlebot3_autorace_2020.world
│   │       ├── turtlebot3_autorace.world
│   │       ├── turtlebot3_house.world
│   │       ├── turtlebot3_stage_1.world
│   │       ├── turtlebot3_stage_2.world
│   │       ├── turtlebot3_stage_3.world
│   │       ├── turtlebot3_stage_4.world
│   │       └── turtlebot3_world.world
│   └── turtlebot3_simulations
│       ├── CHANGELOG.rst
│       ├── CMakeLists.txt
│       └── package.xml
├── turtlebot_camera_bringup
│   ├── CMakeLists.txt
│   ├── launch
│   │   ├── aruco_on_turtlebot_test.launch
│   │   ├── aruco_startup.launch
│   │   └── camera_bringup.launch
│   └── package.xml
├── turtlebot_target_follow
│   ├── CMakeLists.txt
│   ├── include
│   │   └── turtlebot_target_follow
│   │       └── target_follow.hpp
│   ├── launch
│   │   ├── follower_simulation.launch
│   │   ├── target_follow_start.launch
│   │   ├── turtlebot_bringup.launch
│   │   └── turtlebot_sim_mimic.launch
│   ├── package.xml
│   ├── src
│   │   ├── target_follow.cpp
│   │   ├── target_follow.cpp.save
│   │   └── target_follow_node.cpp
│   └── turtlebot_bringup.launch.save
├── turtle_Project_simulation
│   ├── turtlebot3_project_bringup
│   │   ├── CMakeLists.txt
│   │   ├── include
│   │   │   └── turtlebot3_project_bringup
│   │   ├── launch
│   │   │   ├── ar_bringup.launch
│   │   │   └── two_turtlebot_bringup.launch
│   │   ├── package.xml
│   │   └── src
│   ├── turtlebot_aruco_driver
│   │   ├── CMakeLists.txt
│   │   ├── include
│   │   │   └── turtlebot_aruco_driver
│   │   ├── launch
│   │   │   └── aruco_driver_bringup.launch
│   │   ├── package.xml
│   │   └── src
│   └── turtlebot_description
│       ├── CMakeLists.txt
│       ├── materials
│       │   ├── scripts
│       │   │   └── image.material
│       │   └── textures
│       │       ├── ar_tag.png
│       │       └── white.jpg
│       ├── meshes
│       │   ├── ar2.jpg
│       │   ├── ar.dae
│       │   └── ar.jpg
│       ├── package.xml
│       ├── urdf
│       │   ├── ar.urdf.xacro
│       │   ├── camera.gazebo.xacro
│       │   ├── turtlebot3_ar.urdf.xacro
│       │   └── turtlebot3_camera.urdf.xacro
│       └── world
│           └── turtle_world.world
└── vision_msgs
    ├── CHANGELOG.rst
    ├── CMakeLists.txt
    ├── include
    │   └── vision_msgs
    │       └── create_aabb.h
    ├── LICENSE
    ├── msg
    │   ├── BoundingBox2D.msg
    │   ├── BoundingBox3D.msg
    │   ├── Classification2D.msg
    │   ├── Classification3D.msg
    │   ├── Detection2DArray.msg
    │   ├── Detection2D.msg
    │   ├── Detection3DArray.msg
    │   ├── Detection3D.msg
    │   ├── ObjectHypothesis.msg
    │   ├── ObjectHypothesisWithPose.msg
    │   └── VisionInfo.msg
    ├── package.xml
    ├── README.md
    └── test
        ├── CMakeLists.txt
        └── main.cpp

'''
__Installation__
To install the package, clone the repository into a catkin workspace.

__Package Descriptions__
------------------------------------------------
__turtlebot_target_follow__  
This package contains the hpp and cpp code for the turtlebot target following. It is the main package of the project.  
	
It parses the /fiducial_transforms (transformation from the raspicam on the turtlebot to detected fiducial markers) rostopic and publishes /cmd_vel (wheel velocity commands for the turtlebot) for both physical and simulated turtlebots.   
	
The package minimizes the angle between the turtlebot and the detected fiducial transform. If the robot loses the fiducial marker from the left side of the camera, it makes the robot rotate left. If the robot loses the fiducial marker from the right side of the camera, it makes the robot rotate right. Also, if the fiducial transform gets too close to the camera (< 0.7 meters from the camera), then it makes the turtlebot back up.  
	
	
__turtle_Project_simulation (directory)__  

__--> turtlebot_description__  

This package contains files required for 3D model descriptions for the turtlebots and AR tag.  
	
__--> turtlebot3_project_bringup__  

This package contains launch files required to spawn a follower turtlebot and AR tag leader Turtlebot in gazebo.  
	
__--> turtlebot_aruco_driver__  

This package contains launch file to run the aruco AR tag detection purely in simulation.  
	

__turtlebot_camera_bringup__  

This package contains launch files to start the raspicam on the turtlebot and launch aruco AR tag detection




__Running the project__
------------------------------------------------

__Running the tracker on the physical Turtlebot__
1. Ensure the ROS_MASTER_URI and ROS_HOSTNAME are appropriately set on the turtlebot and main pc such that the ROS_MASTER_URI matches on both machines and the ROS_HOSTNAME matches the machines IP address

2. Run the following commands in your main pc's terminal:  
```echo 'export LDS_MODEL=LDS-01' >> ~/.bashrc```
	
```echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc```
	
4. In workspace, run:  
The following instructions assume that a catkin workspace has been created at '$WORKSPACE' and the source path os at `$WORKSPACE/src`
```catkin build turtlebot_target_follow```  
	
```
source $WORKSPACE/devel/setup.bash

# Replace $WORKSAPCE with the appropriate worksapce path
```

5.  Run roscore on either turtlebot or your machine (depending on which has the MASTER_URI)

6. ssh to turtlebot and run:  
	
```roslaunch turtlebot_target_follow turtlebot_bringup.launch```

This will launch the raspicamera, do the image transport needed for the ar tag processing node, and launch the turtlebot3_robot.bringup which starts all the motor drivers, gryo, etc on the turtlebot. 

7. On main computer run:  
	
```roslaunch turtlebot_target_follow target_follow_start.launch```
This starts the aruco package which handles the ar tag transforms, gazebo client with a simulated turtlebot mimicing the real one, and the target_follow_node which reads in the ar tag transform and sends appriopriate motor commands to the cmd_vel topic for the turtlebot and mimic to move.

To change the size of the ar tag to match that of your actual ar tag size change the fiducial_length rosparam via:  
	
```roslaunch turtlebot_target_follow tartget_follow_start fiducial_length:= #tag side length in meters```
  
___Usage with Gazebo Simulation___
There are launch files which allows to run the simulation only version of the task with gazebo.
	
```roslaunch turtlebot_target_follow follower_simulation.launch```
  
__To run ar tag vizualiation seperately__
	
__Launch camera__  
	
```roslaunch raspicam_node camerav2_1280x960.launch```

__Image transpost converts the images into suitable compressed format to use for ar tag tracking__
	
```rosrun image_transport republish compressed in:=/raspicam_node/image raw out:=/raspicam_node/image/image_repub```

__Launches Ar Tag Track__
	
```roslaunch aruco_detect aruco_detect.launch transport:=compressed verbose:=true```

__Use rqt_gui to visualize__
	
```rosrun rqt_gui rqt_gui```
