# Access Multiple CANstress Devices from a Single Test Module

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

1. Open the [CANstress](../../CANoeCANalyzer/Ribbon/File/Options/Extensions/ExtensionsCANstress.md) page in the **Extensions** section.
2. Adjust the RS232 settings if necessary when using a CANstress device connected via RS232.
3. Close and reopen the **CANoe** options. Now all connected CANstress devices should be listed in the table.
4. Configure CANstress devices by clicking the button over the table as described on the page. If you want to access the devices using an alias, set the alias in the first column.

Please also note the information on help page [CANstress and Distributed Mode/VN8900](CAPLfunctionsCANstressCANoeRTVN890.md) if you are using [distributed mode](../../CANoeCANalyzer/RTSetup/DistributedMode/DistributedModeConcept.md) or a [VN8900](../../CANoeCANalyzer/Interfaces/VN8900/VN8900.md).

To establish a connection to a specific CANstress device, you need to use the **CANstressCreateServer** command with the alias or number of a configured CANstress device as a parameter. You will then obtain a handle, which you can use to switch between different devices. To do this, you need to use the [CANstressSetDevice](Functions/CAPLfunctionCANstressSetDevice.md) function with the relevant handle as a parameter.

The modeling library will **recognize** the set CANstress device. When **CANstressCreateServer** or **CANstressSetDevice** is called, the following calls to CANstress CAPL functions are executed on the set device.

**Example**

```plaintext
// Check that CANstress devices have been configured
if (CANstressAvailableDevices() < 2)
{
    TestCaseFail();
    Write("Number of configured CANstress devices is less than 2!");
}

// Establish connection to "cstCAN1"
deviceId1 = CANstressCreateServer("cstCAN1");
CANstressConnect();

// Establish connection to "cstCAN2"
deviceId2 = CANstressCreateServer("cstCAN2");
CANstressConnect();

// The following commands are executed on "cstCAN2"
CANstressOpen(".\\CANstress\\EngineData_BusOff.cst");

CANstressSetDevice(deviceId1);

// The following commands are executed on "cstCAN1"
CANstressOpen(".\\CANstress\\EngineData_BusOff.cst");
```
