[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionAvbConnect.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **AvbConnect**

# AvbConnect

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `dword AvbConnect(dword talkerHandle, byte remoteMacAddress[], char onConnectCallback[]); // form 1`
- `dword AvbConnect(dword talkerHandle, dword remoteIpV4Address, dword port, char onConnectCallback []); // form 2`
- `dword AvbConnect(dword talkerHandle, byte remoteIpV6Address[], dword port, char onConnectCallback []); // form 3`
- `dword AvbConnect(dword talkerHandle, onConnectCallback []); // form 4`

## Description

The function establishes a connection with the specified location. If the connect operation does not complete immediately the operation is performed asynchronously and the function will return 460609. In this case the passed CAPL callback [OnAvbConnect](CAPLfunctionOnAvbConnect.md) will be called on completion (successful or not).

**Used transport protocols:**

- **AVTP** for form 1
- **RTP via UDP** for form 2 and 3
- **RTSP via TCP** for form 4

## Parameters

- **talkerHandle**: The Talker handle.
- **remoteMacAddress**: The (6 byte) destination MAC address (usually a multicast address).
- **remoteIpV4Address**: The (4 byte) destination IPv4 address (usually a multicast address).
- **remoteIpV6Address**: The (16 byte) destination IPv6 address (usually a multicast address).
- **onConnectCallback**: The name of the CAPL callback function (see [OnAvbConnect](CAPLfunctionOnAvbConnect.md)).

## Return Values

- **0**: The function completed successfully.
- **460609**: The operation is pending and will be completed later.
- **Any other value**: Other [error code](../CAPLfunctionsAVBILErrorCode.md).

## Example

—

[See Also](javascript:void(0);)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
