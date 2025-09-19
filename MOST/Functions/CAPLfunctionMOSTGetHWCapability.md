[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetHWCapability.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetHWCapability

# mostGetHWCapability

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostGetHWCapability(long channel, long capID);
```

## Description

`mostGetHWCapability()` can be used to query the properties of the MOST interface used.

## Parameters

- **channel**: Channel of the connected interface.
- **capID**: The ID decides the meaning of the return value.

  - **kMostHWCap_MaxNumberOfInstances = 0**: >0 - Number of interfaces of this type being used simultaneously
  - **kMostHWCap_MaxWriteOS8104Registers = 1**: >=0 - Number of OS8104 registers that can be written with a command
  - **kMostHWCap_MaxReadOS8104Registers = 2**: >=0 - Number of OS8104 registers that can be read with a command
  - **kMostHWCap_TwinklePowerLed = 3**: 0, 1 - 1: The mostTwinklePowerLed command functions with the interface
  - **kMostHWCap_LightLockStress = 4**: 0, 1 - 1: The mostGenerateLightError and mostGenerateLockError commands function with the interface
  - **kMostHWCap_CtrlNode = 8**: 0, 1 - 1: Can be operated in Node Mode for the control channel (sending/receiving control messages)
  - **kMostHWCap_CtrlSpy = 9**: 0, 1 - 1: Can be operated in Spy Mode for the control channel
  - **kMostHWCap_CtrlNodeAndSpySimultaneous = 10**: 0, 1 - 1: Can be operated simultaneously in Node and Spy Mode (control channel)
  - **kMostHWCap_CtrlNodeAndSpyEventDoubling = 11**: 0, 1 - 1: Always generates node and spy message for a received message from the control channel
  - **kMostHWCap_CtrlRxBufferFullSimulation = 12**: 0, 1 - 1: The mostSetRxBufferCtrl command functions with the interface
  - **kMostHWCap_AsyncNode = 16**: 0, 1 - 1: Can be operated in Node Mode for the asynchronous channel
  - **kMostHWCap_AsyncSpy = 17**: 0, 1 - 1: Can be operated in Spy Mode for the asynchronous channel
  - **kMostHWCap_AsyncNodeAndSpySimultaneous = 18**: 0, 1 - 1: Can be operated simultaneously in Node and Spy Mode (asynchronous channel)
  - **kMostHWCap_AsyncNodeAndSpyEventDoubling = 19**: 0, 1 - 1: Always generates node and spy message for a received message from the asynchronous channel
  - **kMostHWCap_SyncAnalogInChannels = 24**: >=0 - Number of analog-in channels (16 bit stereo)
  - **kMostHWCap_SyncAnalogOutChannels = 25**: >=0 - Number of analog-out channels (16 bit stereo)
  - **kMostHWCap_SyncAnalogInMute = 26**: 0, 1 - 1: Can mute the analog-in channel
  - **kMostHWCap_SyncAnalogOutMute = 27**: 0, 1 - 1: Can mute the analog-out channel
  - **kMostHWCap_SyncAllocTableReporting = 28**: 0, 1 - 1: Reports changes to the allocation table

## Return Values

- **>=0**: Property value
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostGetHWInfo](CAPLfunctionMOSTGetHWInfo.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
