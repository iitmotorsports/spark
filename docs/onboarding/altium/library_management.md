# Altium Library Management

IIT Motorsports keeps an extensive catalog of parts for our schematics and PCBs. To ensure accurate circuit design and board production, it is imperitive that the data for these parts is entered correctly. We use the standardizations and instructions as listed below in order to maintain our parts library.

We store all of our parts in our [Altium 365](https://www.altium.com/altium-365) cloud instance. This reduces the dependency on manually shared libraries for our contributors. All libraries are automatically synchronized between Altium instances.


Our components are split up into the following categories:

??? info "Component Categories"
    * Audio
    * Batteries
    * Capacitors
    * Connectors
    * Crystals & Oscillators
    * Data Converters
    * Diodes
    * Fuses
    * Inductors
    * Integrated Circuits
        - Amplifiers
        - Clock & Timing
        - Drivers
        - Interface
        - Logic
        - Memory
        - Power Supply
        - Processors
        - Wireless
    * LED
    * Logics
    * Mechanical
    * Microcontrollers
    * Miscellaneous
    * Optoelectronics
    * Radio & RF
    * Relays
    * Resistors
    * Switches
    * Test Points
    * Transformers
    * Transistors

## Install Component Helpers

We get the majority of our components from the Altium Component Library. We use alternate component libraries when the part is not in the altium library.

We use the following methods to retrieve components for Altium:

* Altium Component Library (Recommended)
* [SnapEDA](https://snapeda.com)
* [Ultra Librarian](https://www.ultralibrarian.com)

In order to make downloading components from SnapEDA and Ultra Librarian easy, we recommend installing the import tool for these libraries.

### Install SnapEDA

1. Exit Altium Designer.
2. Grab SnapEDA Altium Plugin from [https://www.snapeda.com/plugins/](https://www.snapeda.com/plugins/).
3. Unzip the file.
4. Run the `.exe` installer.
5. Once installed, run Altium Designer and open SnapEDA using the button at the top.
![](/assets/onboarding/altium/library_management/snapeda.png)
6. Sign in to SnapEDA.
7. Open settings and change the library path to a known folder. You'll need to navigate to this folder each time you import a part from SnapEDA. We recommend: `{your_user}/Documents/SnapEDAImport`.
![](/assets/onboarding/altium/library_management/snapeda_settings.png)

## How to Find, Upload, and Use components

In order to find components, we use the following method:

![](/assets/onboarding/altium/library_management/component_flowchart.svg)