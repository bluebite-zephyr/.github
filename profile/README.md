# Welcome to BlueBite

Welcome to the official GitHub organization for the **BlueBite** Zephyr support ecosystem! 

The **BlueBite** family of development boards are designed around the popular **Adafruit Feather form factor**, allowing you to easily expand your project's capabilities using a wide variety of "Wings" via the Zephyr RTOS shield system. Our current flagship is the **BlueBite54**, powered by the **Nordic Semiconductor nRF54L15** SoC.

Our repositories provide out-of-the-box support for the **nRF Connect SDK (NCS)** (based on the **Zephyr RTOS**), structured as modular `west` workspaces so you can get up and running immediately.

---

## Core Repositories: Hardware & Drivers

These repositories contain the fundamental building blocks for using the BlueBite ecosystem, including board definitions, devicetree overlays, and custom drivers.

* **[bluebite-hw](https://github.com/bluebite-zephyr/bluebite-hw)**
    The core board support repository. It contains the Zephyr board folders for all supported **BlueBite** variants, as well as the shield definitions for our supported Feather Wings.
* **[bluebite-drivers](https://github.com/bluebite-zephyr/bluebite-drivers)**
    The custom driver repository. It houses all out-of-tree drivers required by the **BlueBite** family of boards and its supported Wings, ensuring seamless integration with Zephyr's device model.

---

## Workspaces & Samples

We provide several `west` workspace repositories tailored to specific use cases. Each sample is pre-configured for the nRF Connect SDK (NCS) and demonstrates how to leverage the features and expansion Wings of the **BlueBite** ecosystem.

* **[bluebite-sample](https://github.com/bluebite-zephyr/bluebite-sample)**
    **The best place to start.** This foundational sample helps you verify your setup and test the basic onboard hardware of the **BlueBite54**. 
* **[audio-echo-sample](https://github.com/bluebite-zephyr/audio-echo-sample)**
    A local audio loopback sample for the **MAX9867 Wing**. It initializes the codec and routes microphone input directly to both playback channels.
* **[fem-sample](https://github.com/bluebite-zephyr/fem-sample)**
    A sample demonstrating how to integrate and use a Front-End Module (FEM) Wing. It is pre-configured for the optional **nRF21540 Wing** to boost your RF range.
* **[walkietalkie-sample](https://github.com/bluebite-zephyr/walkietalkie-sample)**
    An advanced Bluetooth LE Audio sample. This project configures two **BlueBite54** devices to act as walkie-talkies using an optional stereo codec Wing (e.g., the **MAX9867 Wing**).
* **[lora-sample](https://github.com/bluebite-zephyr/lora-sample)**
    A sample demonstrating long-range communication using LoRa. This project utilizes the Zephyr USP within NCS and is configured to work with a LoRa Wing (e.g., the **LR1121 Wing**).

---

## Getting Started

Because our samples act as independent `west` workspaces, getting started is as simple as initializing the workspace of your choice.

To try out the basic sample, run the following commands:

```bash
# Initialize the west workspace
west init -m https://github.com/bluebite-zephyr/bluebite-sample --mr main my-bluebite-workspace

# Move into the workspace directory
cd my-bluebite-workspace

# Update and fetch all necessary modules (including NCS, Zephyr, and BlueBite core repos)
west update
```

From there, you can build and flash using standard `west build` and `west flash` commands tailored to your specific **BlueBite** board target. Be sure to check the specific `README.md` inside each sample repository for detailed build instructions and shield configurations.

---

*Happy Hacking!*
