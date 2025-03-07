[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILUnfreezeTp.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILUnfreezeTp

# J1939ILUnfreezeTp

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILUnfreezeTp(dword protocol, dword sa, dword da); //Form 1`
- `long J1939ILUnfreezeTp(dbNode node, dword protocol, dword sa, dword da); //Form 2`

## Description

Unfreezes (resumes) the current transport protocol (BAM, RTS/CTS) connection that matches the given protocol, source address, and destination address. The source address specifies the originator (the node sending RTS or BAM) and the destination address specifies the receiver (the node sending CTS, or 255 for BAM) of a connection. If the connection was not found, an error will be returned.

Only a connection that has been frozen by [J1939ILFreezeTp](CAPLfunctionJ1939ILFreezeTp.md) can be resumed.

The connection then acts as if no interruption occurred. That means, if the connection was frozen in a state waiting for a response, the connection will wait for that exact response after it is resumed. Timeouts of the connection resume with the remaining amount of time.

## Parameters

- **node**: Simulation node to apply the function.
- **protocol**:
  - 1: BAM
  - 2: RTS/CTS
  - 3: Fast Packet (not supported)
  - 4: ETP (ISO11783 Interaction Layer)
  - 5: FD TP BAM (not supported)
  - 6: FD TP RTS/CTS (not supported)
- **sa**: 0-255
- **da**: 0-255

## Return Values

- **0**: OK
- **0x050008**: Connection not found

## Example

See [J1939ILFreezeTp](CAPLfunctionJ1939ILFreezeTp.md)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)