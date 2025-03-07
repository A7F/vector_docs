[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/CAPLfunctionsCANstressOverview.md)

[CAPL Functions](../CAPLfunctions.md) » CANstress CAPL Functions

# CANstress CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

To use the CAPL functions the [CANstress_NL.dll](../../CANoeCANalyzer/Interfaces/CANstress.md) must be included.

## Functions Overview

- **CANstressCreateServer**: Starts the CANstress software and establishes a connection via the COM interface to this COM server.
- **CANstressCreateServer(DeviceAlias)**: Starts the CANstress software and establishes a connection to this COM server via the COM interface.
- **CANstressCreateServer(Device number)**: Starts the CANstress software and establishes a connection to this COM server via the COM interface. This function must be called before all other CANstress CAPL functions!
- **CANstressAvailableDevices**: Indicates the number of configured CANstress devices.
- **CANstressConnect**: Establishes a connection between the CANstress software and the CANstress hardware.
- **CANstressGetDevice**: Sends back the handle for the current CANstress device.
- **CANstressGetInfo**: Delivers information about CANstress software and the connected CAN hardware.
- **CANstressGetPerformedDisturbances**: Acquires the number of disturbances that were executed by CANstress.
- **CANstressIsFinished**: Serves to query whether the CANstress hardware is in the state **Finished**.
- **CANstressIsIdle**: Serves to query whether the CANstress hardware is in the state **Idle**.
- **CANstressIsPending**: Serves to query whether the CANstress hardware is in the state **Pending**.
- **CANstressOnFinished**: Registers a CAPL function as callback that is called if CANstress is switched into the state **Finished**.
- **CANstressOnIdle**: Registers a CAPL function as callback that is called if CANstress is switched into the state **Idle**.
- **CANstressOnPending**: Registers a CAPL function as callback that is called if CANstress is switched into the state **Pending**.
- **CANstressOpen**: Opens a CANstress configuration file.
- **CANstressQuit**: Ends the CANstress software.
- **CANstressSetBTR**: Sets the value of the **Bus Timing Register**.
- **CANstressSetContinuousDisturbanceTimeLimited**: Sets the **Continuous disturbance (time limited) mode**.
- **CANstressSetContinuousDisturbanceUntilStop**: Sets the **Continuous disturbance (until stop) mode**.
- **CANstressSetContinuousDisturbanceWhileTrigger**: Sets the **Continuous disturbance (while trigger) mode**.
- **CANstressSetDevice**: Defines the active device for further functions.
- **CANstressSetDisturbanceSequence**: Sets the disturbance sequence.
- **CANstressSetLimitedDisturbanceNumber**: Sets the **Limited number of disturbances disturbance mode**.
- **CANstressSetResistor**: Sets the value of a resistor for analog disturbances.
- **CANstressSetTriggerId**: Sets the message ID, which will activate the trigger.
- **CANstressSetTriggerRange**: Sets a range for message IDs, which will activate triggers.
- **CANstressSetUnlimitedDisturbanceNumber**: Sets the **Unlimited number of disturbances disturbance mode**.
- **CANstressStart**: Orders the CANstress COM server to activate the hardware for the error disturbance activity.
- **CANstressStop**: Orders the CANstress COM server to end the current disturbance activity of the hardware.
- **CANstressStopTrigger**: Deactivates the CANstress software triggers if this is still active.
- **CANstressTrigger**: Activates the CANstress software trigger.
- **CANstressWaitForFinished**: Waits until the CANstress hardware is in the state **Finished**.
- **CANstressWaitForIdle**: Waits until the CANstress hardware is in the state **Idle**.
- **CANstressWaitForPending**: Waits until the CANstress hardware is in the state **Pending**.

[Access Multiple CANstress Devices from a Single Test Module](CAPLfunctionsCANstressAccessMultipleCANstressDevices.md) • [CANstress and Distributed Mode](CAPLfunctionsCANstressCANoeRTVN890.md) • [CANstress: Main Test Function Example](CAPLfunctionsCANstressMainTestFunctionExample.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)