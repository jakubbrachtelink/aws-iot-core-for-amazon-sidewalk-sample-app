Connect the AIOT-DK1 board to the PC via the J12 connector, as shown below.

![AIOT-DK1 and PC Connection](AIOT-DK1andPCConnection.jpg){height=300px}

Start the BDT tool.

![Select the Onboard Programmer](sellect_internal_programmer.png)

Make sure the hardware has been detected by the BDT tool. If the panel (1) is empty, click “Install Drivers” (2) and follow the instructions.

![BDT Hardware Selection](BDT_hw_connect.png)

Ensure the `TL323X` chip family is selected (1), click "Activate"(2), and make sure communication with the target is established (3).

![BDT Activate](BDT_activate.png)

To bring the hardware to a defined and predictable state, it is recommended to erase the entire flash memory. Open the configuration panel (1), enter the flash memory size (2), enable “Unlock flash prior to erase” (3), click “ERASE” (4), and monitor the progress (5).

![BDT Erase](BDT_erase.png){height=400px}

**Note:**

>- Do not erase memory above 0xF8000 (992 KB). Some entries, such as factory calibration data, may be corrupted.


To run the demo application, the flash memory should contain the following two entities:

- Application binary (the actual application, executable machine code)
- MFG binary (contains binary blob)


Load the demo application (1) and the MFG blob (2) into the BDT tool. Make sure the download addresses are correct: Application = 0x000000, MFG = 0x0F9000 (3).

Click “Download” (4) and monitor the progress (5).

![Download](BDT_programming_app.png){height=400px}

Reset the board and enjoy the demo