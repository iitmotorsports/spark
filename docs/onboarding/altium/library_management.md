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

### Step 1 - Check Components Panel

The components panel represents all components that we've used and uploaded to our Altium 365 instance. This should be the first place you check for components. Any component that is created must be added to the components bin in order to be properly synced and used for all projects.

* Make sure that the IIT Motorsports Fusion 365 instance is active by clicking the cloud icon in the upper-right hand corner.
* Ensure that the box above the search bar is set to `All` which will automatically pull components from the Fusion 365 instance.

![](/assets/onboarding/altium/library_management/components_panel.png)

✅ If the part is found, then it can be dragged into the active project and you're done.

❌ If the part is not found, then move onto [Step 2 - Check Manufacturer Part Search](#step-2-check-manufacturer-part-search)

### Step 2 - Check Manufacturer Part Search

The manufacturer part search is an integrated component library solution that allows you to easily import popular components into Altium. 

Here's the following steps to import a component. We will be using a [Rohm Semiconductor RED SMD LED](https://www.digikey.com/short/58dwr87b) for this example.

1. Open the `Manufacturer Part Search` panel and search for the desired component. The green semiconductor symbol next to the component indicates whether it has a symbol and footprint available which is required to make the component.
!!! warning

    If the component does not have the green semiconductor symbol, then the part does not have the data necessary to make the component. Move onto [Step 3 - Check SnapEDA](#step-3-check-snapeda).

![](/assets/onboarding/altium/library_management/mps_search.png)

2. Click the arrow next to download, then select `Acquire...`.
![](/assets/onboarding/altium/library_management/mps_acquire.png)

3. Select the type of the component. For this example, we'll be adding the component to the LED category.
![](/assets/onboarding/altium/library_management/mps_type.png)

4. The menu will prompt you to accept the component data. We recommend that you only select one datasheet from the list to avoid uploading more data than necessary. Click Okay.
![](/assets/onboarding/altium/library_management/mps_data.png)

5. The Manufacturer Part Search will automatically fill out all of the necessary information. Unless any further changes are necessary, the component is ready to be uploaded. Right-Click the upper tab and click save, or use ++ctrl+s++. This will only save the component locally, **and not to the cloud**.
![](/assets/onboarding/altium/library_management/mps_save.png)

6. The component is ready to be uploaded to the cloud. Right-click the component tab and click `Close.` When prompted, save the component to the server. When asked for release notes, click Okay. 
![](/assets/onboarding/altium/library_management/mps_close.png)
![](/assets/onboarding/altium/library_management/mps_save_to_server.png)
![](/assets/onboarding/altium/library_management/mps_release.png)

✅ The part has been successfully added and saved to the cloud. The component can be added **from the components bin** into the active project and you're done!

### Step 3 - Check SnapEDA

SnapEDA is a popular third-party component library. SnapEDA has an extensive catalog of parts for companies like TE Connectivity and Amphenol. If the [Check Manufacturer Part Search](#step-2-check-manufacturer-part-search) doesn't have the component, we check SnapEDA for the part next.

!!! note

    Make sure you have the directory you set for SnapEDA in the [Install Component Helpers](#install-component-helpers) step ready as it'll be necessary here.
    
Here's the following steps to import a component using SnapEDA. We will be using a [TE Connectivity 2 Position Header (5-103635-1)](https://www.digikey.com/short/499mq44m) for this example.

!!! warning

    If the component does not have the semiconductor and footprint symbol **both** illuminated, then the part does not have the data necessary to make the component. Move onto [Step 4 - Check Ultra Librarian](#step-4-check-ultra-librarian).

1. Open the `SnapEDA` panel and search for the desired component. 
    ![](/assets/onboarding/altium/library_management/snapeda.png)
    ![](/assets/onboarding/altium/library_management/snapeda_search.png)

1. Download the component to your local computer. It is imperitive that you download the part instead of placing it. If the part is placed directly, then it won't be uploaded to the Altium 365 cloud.    
    ![](/assets/onboarding/altium/library_management/snapeda_download.png)
    ![](/assets/onboarding/altium/library_management/snapeda_savepart.png)
    ![](/assets/onboarding/altium/library_management/snapeda_atl.png)

1. Navigate to the folder that you set for SnapEDA. There should be two files there with the same part number as the component.
    ![](/assets/onboarding/altium/library_management/snapeda_folder.png)

Remember where these files are stored, and move on to [Step 5 - Upload Component to Altium 365](#step-5-upload-component-to-altium-365).

### Step 4 - Check Ultra Librarian

Ultra Librarian is another online component library that can export files for Altium. We often find quality issues with the files provided by Ultra Librarian. At this stage, we recommend considering making the [component from scratch](https://www.altium.com/documentation/altium-designer/creating-new-component).  



### Step 5 - Upload Component to Altium 365

1. Open Library Importer, navigate to the folder with the component files, and select the two files with the corresponding part name.
    ![](/assets/onboarding/altium/library_management/snapeda_library_importer.png)
    ![](/assets/onboarding/altium/library_management/snapeda_imp_choose.png)
    ![](/assets/onboarding/altium/library_management/snapeda_imp_open.png)
1. Set the type of the component, then click `Import`.
    ![](/assets/onboarding/altium/library_management/snapeda_imp_type.png)
    ![](/assets/onboarding/altium/library_management/snapeda_imp_import.png)

!!! warning

    Imported files are often missing necessary data and models. The component imported using the method above must be re-edited in order to add the missing data.

    Follow these steps to add conclusive component data:
    
    1. Go to the `Components` panel and search for the component you just uploaded. Right click on the component and click Edit.
        ![](/assets/onboarding/altium/library_management/confirm_edit.png)
    1. Check the Part Choices box. If this is empty:

        * Click the add button.

            ![](/assets/onboarding/altium/library_management/confirm_part_choices.png)

        * Find the correct part data from the list. Altium should automatically search for the part number, but manual searching may be necessary in certain cases.

            ![](/assets/onboarding/altium/library_management/confirm_part_choices_select.png)

        * Select all checkboxes under parameters. We recommend you only select one datasheet since they are most likely duplicates of each other. Then click Okay.

            ![](/assets/onboarding/altium/library_management/confirm_part_choices_okay.png)
    1. The component is ready to be uploaded to the cloud. Right-click the component tab and click `Close.` When prompted, save the component to the server. When asked for release notes, click Okay. 
        ![](/assets/onboarding/altium/library_management/mps_close.png)
        ![](/assets/onboarding/altium/library_management/mps_save_to_server.png)
        ![](/assets/onboarding/altium/library_management/mps_release.png)
