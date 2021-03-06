# SocketCAN Demo Programs

These programs demonstrate how to use the SocketCAN API on Linux. You are free
to use these as a starting point for writing your own SocketCAN enabled
applications.

## Cross Compilation

### O3D3xx

To cross compile this demo code to run it on an O3D3xx you have to install the provided toolchain to ``/opt/poky/1.8.1`` first. If you do not install the toolchain to its default PATH please adjust the [cmake/toolchains/o3d3xx.cmake](cmake/toolchains/o3d3xx.cmake) file accordingly.

```
$ mkdir build
$ cd build
$ cmake -DCMAKE_TOOLCHAIN_FILE=../cmake/toolchains/o3d3xx.cmake ../
```

## Raw Interface Demo

This program demonstrates reading and writing to a CAN bus using SocketCAN's
Raw interface. The intended behavior of this program is to read in any CAN
message from the bus, add one to the value of each byte in the received
message, and then write that message back out on to the bus with the message ID
defined by the macro MSGID.

## Broadcast Manager Interface Demo

This program demonstrates reading and writing to a CAN bus using SocketCAN's
Broadcast Manager interface. The intended behavior of this program is to read
in CAN messages which have an ID of 0x123, add one to the value of each data
byte in the received message, and then write that message back out on to the
bus with the message ID defined by the macro MSGID.

## Broadcast Manager Cyclic Demo

This program demonstrates sending a set of cyclic messages out on to the CAN
bus using SocketCAN's Broadcast Manager interface. The intended behavior of
this program is to send four cyclic messages out on to the CAN bus. These
messages have IDs ranging from 0x0C0 to 0x0C3. These messages will be sent out
one at a time every 1200 milliseconds. Once all messages have been sent,
transmission will begin again with message 0x0C0.

