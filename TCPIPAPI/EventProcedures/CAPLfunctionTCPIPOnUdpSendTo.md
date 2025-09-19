[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/EventProcedures/CAPLfunctionTCPIPOnUdpSendTo.md)

**CAPL Functions** » **TCP/IP API** » **OnUdpSendTo**

# OnUdpSendTo

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnUdpSendTo( dword socket, long result, char buffer[], dword size);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
void OnUdpSendTo( UdpSocket socket, long result, char buffer[], dword size);
```

## Description

If the CAPL program implements this callback it is called when an asynchronous send operation on an UDP socket completes.

## Parameters

- **socket**: The socket handle or socket object.
- **result**: The result code of the asynchronous operation. If the operation completed successfully the value is 0. Otherwise the value is an [error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md).
- **buffer**: The buffer provided with the send operation.
- **size**: The number of bytes sent.

## Return Values

—

## Example

See example [Create UDP Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md#UDPServerSocket).

[UdpSendTo](../Functions/CAPLfunctionUDPSendTo.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
