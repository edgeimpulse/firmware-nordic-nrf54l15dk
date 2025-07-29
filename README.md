# Edge Impulse firmware for Nordic Semiconductor nRF54LXX DK

[Edge Impulse](https://www.edgeimpulse.com) enables developers to create the next generation of intelligent device solutions with embedded Machine Learning. This repository contains the Edge Impulse firmware for the Nordic Semiconductor nRF54L15DK development board, in combination with the sensors. This combination supports all Edge Impulse device features, including ingestion and inferencing.

> **Note:** Do you just want to use this development board with Edge Impulse? No need to build this firmware. See the instructions for the [nRF54L15DK](https://docs.edgeimpulse.com/docs/development-platforms/officially-supported-mcu-targets/nordic-semi-nrf54Ll15-dk) for prebuilt images and instructions, or use the [data forwarder](https://docs.edgeimpulse.com/docs/tools/edge-impulse-cli/cli-data-forwarder) to capture data from any sensor.

> **Note:** This firmware is complatible with NCS 3.0.0

## Building the device firmware (locally)

1. Install the [nRF Connect SDK](https://docs.nordicsemi.com/bundle/ncs-3.0.0/page/nrf/getting_started/installing.html) in a *separate* folder from this repository (e.g. `~/repos/ncs`).

2. Clone this repository:

    ```bash
    $ git clone https://github.com/edgeimpulse/firmware-nordic-nrf54lxx
    ```

3. Build the application:

    ```bash
    $ west build -b nrf54l15dk/nrf54l15/cpuapp
    ```

## Building the device firmware (Docker)

1. Clone this repository:

    ```bash
    $ git clone https://github.com/edgeimpulse/firmware-nordic-nrf54lxx
    ```

2. Build the Docker container:

    ```bash
    $ docker build -t edge-impulse-nordic .
    ```

3. Build the application:

    ```bash
    $ docker run --rm -v $PWD:/app edge-impulse-nordic west build -b nrf54l15dk/nrf54l15/cpuapp

## Flashing

1. Connect the board and power it on.
2. Copy `build/zephyr/zephyr.bin` to the `JLINK` mass storage device.

## Flashing (command line)

1. Connect the board and power on.
2. Flash the board controller firmware:

    ```bash
    $ west flash
    ```
