# Vscode Matter Dev Container

The docker image `espressif/esp-matter:latest_idf_v5.2.1` is very large(15gb), but has everything required for building the projects. View the image at [docker](https://hub.docker.com/r/espressif/esp-matter/tags).

To start, install [the required vscode extensions](https://github.com/espressif/vscode-esp-idf-extension/blob/master/docs/tutorial/wsl.md#visual-studio-code). With `ctrl+shift+p` search for `Dev Containers: Rebuild and Reopen in Container`

## USB flashing/monitoring/debugging

### Windows

To pass the usb device to the container on a windows host we can use [usbipd](https://github.com/espressif/vscode-esp-idf-extension/blob/master/docs/tutorial/wsl.md#usbipd)

### Linux

The DevContainer has runargs where we can pass the device to the container with: "--device=/dev/ttyACM0"
Connecting the ESP32 to the container in this way allows us to program, monitor the device over UART. With the ESP32S3 we can also use the /dev/ttyACM0 device to debug over JTAG. 

## example: Generic Switch

Use the esp-idf extension to build the project set in `postCreateCommand` devcontainer.json line 28.
It is also possible to open up a terminal and issue commands like `idf.py build`