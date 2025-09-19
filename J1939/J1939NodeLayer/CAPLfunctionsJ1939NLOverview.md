[J1939 Node Layer](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/CAPLfunctionsJ1939NLOverview.md)

**CAPL Functions** » [1939](../CAPLfunctionsJ1939StartPage.md) » J1939 Node Layer

# J1939 Node Layer

**Valid for**: CANoe DE • CANoe4SW DE

## J1939

- Only available with J1939.
- To use the CAPL functions the node layer **J1939_NL.DLL** must be included.
- You can include the node layer by using the configuration dialog of the node on page **Components** or via the node attribute **NodeLayerModules** in the database.

**ON THIS PAGE:**

- [Access Environment Variables](#Access)
- [Callback Functions](#Callback)
- [Network Relevant Functions](#Network)
- [Node Control](#Node)
- [Other Functions](#Other)
- [Send and Receive](#Send)
- [Working Set Master](#WorkingSetMaster)

## Access Environment Variables 

- [J1939GetEnvDbl](Functions/CAPLfunctionJ1939GetEnvDbl.md): Returns the value of an environment variable of type double.
- [J1939GetEnvInt](Functions/CAPLfunctionJ1939GetEnvInt.md): Returns the value of an integer environment variable.
- [J1939SetEnvDbl](Functions/CAPLfunctionJ1939SetEnvDbl.md): Sets the value of an environment variable of type double.
- [J1939SetEnvInt](Functions/CAPLfunctionJ1939SetEnvInt.md): Sets the value of an integer environment variable.

## Callback Functions 

- [J1939AppAddrClaimed](Functions/CAPLfunctionJ1939AppAddrClaimed.md): Indicates that Address Claiming was performed successfully.
- [J1939AppCmdAddrIndication](Functions/CAPLfunctionJ1939AppCmdAddrIndication.md): Indicates that a new address has been assigned to a control device.
- [J1939AppErrorIndication](Functions/CAPLfunctionJ1939AppErrorIndication.md): Indicates that errors have occurred.
- [J1939AppNmtIndication](Functions/CAPLfunctionJ1939AppNmtIndication.md): Is called when an ECU claims an address or an ECU loses its address.
- [J1939AppRequestIndication](Functions/CAPLfunctionJ1939AppRequestIndication.md): Indicates that the "OnRequest" parameter group has been received.
- [J1939AppRxIndication](Functions/CAPLfunctionJ1939AppRxIndication.md): Indicates that a parameter group has been received.
- [J1939AppTxIndication](Functions/CAPLfunctionJ1939AppTxIndication.md): Indicates that a PG has been sent successfully.

## Network Relevant Functions 

- [J1939EnableNameManagement](Functions/CAPLfunctionJ1939EnableNameManagement.md): Activated or deactivated the name management of a node.
- [J1939GetAAC](Functions/CAPLfunctionJ1939Get.md): Returns if a device is self-configuring.
- [J1939GetAddress](Functions/CAPLfunctionJ1939GetAddress.md): Returns the network address of a device.
- [J1939GetBus](Functions/CAPLfunctionj1939getbus.md): Returns a bus handle.
- [J1939GetBusName](Functions/CAPLfunctionj1939getbusname.md): Returns the bus name.
- [J1939GetECUInstance](Functions/CAPLfunctionJ1939Get.md): Returns the ECU instance of a device.
- [J1939GetFct](Functions/CAPLfunctionJ1939Get.md): Returns the function of a device.
- [J1939GetFctInstance](Functions/CAPLfunctionJ1939Get.md): Returns the function instance of a device.
- [J1939GetIG](Functions/CAPLfunctionJ1939Get.md): Returns the industry group of a device.
- [J1939GetIN](Functions/CAPLfunctionJ1939Get.md): Returns the identity number of a device.
- [J1939GetMC](Functions/CAPLfunctionJ1939Get.md): Returns the manufacturer code of a device.
- [J1939GetName](Functions/CAPLfunctionJ1939GetName.md): Returns the name of a device.
- [J1939GetVS](Functions/CAPLfunctionJ1939Get.md): Returns the device class of a device.
- [J1939GetVSInstance](Functions/CAPLfunctionJ1939Get.md): Returns the device class instance of a device.
- [J1939MakeName](Functions/CAPLfunctionJ1939MakeName.md): Creates a J1939 device name.
- [J1939NMTDump](Functions/CAPLfunctionJ1939NMTDump.md): Copies the current state of the network table into a buffer.
- [J1939SetAAC](Functions/CAPLfunctionJ1939Set.md): Sets if a device is self-configuring.
- [J1939SetECUInstance](Functions/CAPLfunctionJ1939Set.md): Sets the ECU instance of a device.
- [J1939SetFct](Functions/CAPLfunctionJ1939Set.md): Sets the function of a device.
- [J1939SetFctInstance](Functions/CAPLfunctionJ1939Set.md): Sets the function instance of a device.
- [J1939SetIG](Functions/CAPLfunctionJ1939Set.md): Sets the industry group of a device.
- [J1939SetIN](Functions/CAPLfunctionJ1939Set.md): Sets the identity number of a device.
- [J1939SetMC](Functions/CAPLfunctionJ1939Set.md): Sets the manufacturer code of a device.
- [J1939SetVS](Functions/CAPLfunctionJ1939Set.md): Sets the device class of a device.
- [J1939SetVSInstance](Functions/CAPLfunctionJ1939Set.md): Sets the device class instance of a device.
- [J1939TableTime](Functions/CAPLfunctionJ1939TableTime.md): Returns the time stamp of the last received "Request for Address Claim".
- [J1939UpdateTable](Functions/CAPLfunctionJ1939UpdateTable.md): Updates the network table.

## Node Control 

- [J1939CreateECU](Functions/CAPLfunctionJ1939CreateECU.md): Sets up a logical node within a CANoe network node.
- [J1939DestroyECU](Functions/CAPLfunctionJ1939DestroyECU.md): Deletes a logical node.
- [J1939ECUGoOffline](Functions/CAPLfunctionJ1939ECUGoOffline.md): Switches the state of the ECU to offline.
- [J1939ECUGoOnline](Functions/CAPLfunctionJ1939ECUGoOnline.md): Stimulates a logical ECU to log on onto the CAN bus.
- [J1939GetEcuState](Functions/CAPLfunctionJ1939GetEcuState.md): Returns the current state of the ECU.
- [J1939GetNodeAddr](Functions/CAPLfunctionJ1939GetNodeAddr.md): Returns the current address of a logical ECU.

## Other Functions 

- [J1939GetLastError](Functions/CAPLfunctionJ1939Getlasterror.md): Returns the last error code.
- [J1939GetLastErrorText](Functions/CAPLfunctionJ1939Getlasterrortext.md): Gets the description of the last error occurred.

## Send and Receive 

- [J1939GetRxData](Functions/CAPLfunctionJ1939GetRxData.md): Receives data of a parameter group.
- [J1939SetTPParam](Functions/CAPLfunctionJ1939SetTPParam.md): Changes the settings of the transport protocol.
- [J1939TxAbort](Functions/CAPLfunctionJ1939TxAbort.md): Interrupts a parameter group transmission.
- [J1939TxReqPG](Functions/CAPLfunctionJ1939TxReqPG.md): Sends a parameter group.

## Working Set Master 

- [J1939GetWSMAddr](Functions/CAPLfunctionJ1939GetWSMAddr.md): Returns the address of the Working Set Master.
- [J1939GetWSMaster](Functions/CAPLfunctionJ1939GetWSMaster.md): Returns the address of the Working Set Master.
- [J1939SetWSMAddr](Functions/CAPLfunctionJ1939SetWSMAddr.md): Set the address of a Working Set Master.

[Error Codes](CAPLfunctionsJ1939NLErrorCodes.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
