Arty-Z7-10-hdmi-out demo
====================

Description
-----------

This project demonstrates how to use the USB-UART Bridge, HDMI Sink and HDMI Source with the ZYNQ processor. Vivado is used to build the demo's hardware platform, and Xilinx SDK is used to program the bitstream onto the board and to build and deploy a C application. Video data streams in through the HDMI in port and out through the HDMI out port. A UART interface is available to configure what is output through HDMI.
There are 3 display frame buffers that the user can choose to display or write to. The configuring options are shown in the table below.

The demo uses the usb-uart bridge to configure the HDMI Display , the Arty Z7-10 must be connected to a computer over MicroUSB, which must be running a serial terminal. For more information on how to set up and use a serial terminal, such as Tera Term or PuTTY, refer to [this tutorial](https://reference.digilentinc.com/learn/programmable-logic/tutorials/tera-term).

| Option    | Function                                                                  |
| --------- | ------------------------------------------------------------------------- |
| 1         | Change the resolution of the HDMI output to the monitor.                  |
| 2         | Changes the frame buffer index.                                           |
| 3/4       | Prints a test pattern in the chosen frame buffer: blended or color bar.   |
| 5         | Inverts current frame colors.                                             |
| 6         | Inverts current frame colors seamlessly.                                  |




Requirements
------------
* **Arty Z7-10**
* **Vivado and Vitis 2020.1 Installations**
* **Serial Terminal Emulator Application**
* **MicroUSB Cable**
* **HDMI Cable**
* **HDMI Capable Monitor/TV**

Demo Setup
----------

1. Download the most recent release ZIP archives from the repo's [releases page](https://github.com/Digilent/Arty-Z7-10-HDMI-Out/releases). These files are called "Arty-Z7-10-HDMI-Out-hw.xpr.zip" and "Arty-Z7-10-HDMI-Out-sw.ide.zip". The -hw archive contains an exported XPR project file and associated sources for use with Vivado. The -sw archive contains exported project files for use with Vitis. Both of these files contain the build products of the associated tool.

  Note: Do not extract the downloaded -sw archive.
  
2. Open Vitis 2020.1. Choose an empty folder as the *Workspace* to launch into.
3. With Vitis opened, click the **Import Project** button, under **PROJECT** in the welcome screen.
4. Choose *Vitis project exported zip file* as the Import type, then click **Next**.
5. **Browse** for the downloaded -sw archive, and **Open** it.
6. Make sure that all boxes are checked in order to import each of the projects present in the archive will be imported, then click **Finish**.
7. Plug in the HDMI cable to the HDMI capable Monitor/TV.
8. Open a serial terminal application (such as [TeraTerm](https://ttssh2.osdn.jp/index.html.en) and connect it to the Arty Z7's serial port, using a baud rate of 115200.
9. In the *Assistant* pane at the bottom left of the Vitis window, right click on the project marked `[System]`, and select **Run** -> **Launch Hardware**. When the demo is finished launching, messages will be able to be seen through the serial terminal, and the demo can be used as described in this document's *Description* section, above.

To later make changes to the Vivado project and update the hardware platform in Vitis:

1. Extract the downloaded -hw archive.
2. Open Vivado 2020.1.
3. Open the XPR project file, found at \<archive extracted location\>/hw/hw.xpr, included in the extracted hardware release in Vivado 2020.1.
4. Make any desired modifications and regenerate the bitstream.
5. Use the File > Export > Export Hardware option to export a hardware platform (XSA) file to a memorable location. Specify the **Fixed** and **Include bitstream** options, as this is a baremetal project and will be used to program the board through Vitis.
6. In Vitis, right click on the *Platform* project, select **Update Hardware Specification**, then navigate to and select the exported XSA for import.
7. Rebuild and relaunch the application.

Next Steps
----------
This demo can be used as a basis for other projects by modifying the hardware platform in the Vivado project's block design or by modifying the SDK application project.

Check out the Arty Z7's [Resource Center](https://reference.digilentinc.com/reference/programmable-logic/arty-z7/start) to find more documentation, demos, and tutorials.

For technical support or questions, please post on the [Digilent Forum](forum.digilentinc.com).

Additional Notes
----------------
For more information on how this project is version controlled, refer to the [digilent-vivado-scripts repo](https://github.com/digilent/digilent-vivado-scripts) and [digilent-vitis-scripts](https://github.com/digilent/digilent-vitis-scripts) repositories.