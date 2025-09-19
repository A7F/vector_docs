[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939ECUGoOnline.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939ECUGoOnline

# J1939ECUGoOnline

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939ECUGoOnline( dword ecuHandle, dword newAddress );
```

## Description

After this function has been called, the logical ECU logs on onto the CAN bus. It must be called separately for each logical ECU.

If it is not possible to log on the first time with Address Claiming, or if the node is "rejected" with a higher priority Address Claiming by the bus at a later point in time, the corresponding error message must be evaluated in [J1939AppErrorIndication()](CAPLfunctionJ1939AppErrorIndication.md). If you want to make a network assignment over the network, the PG "CommandedAddress" can be sent to an ECU.

Use the Null Address (0xFE) to switch the ECU to offline mode. In that explicit case a "Cannot Claim" message ("Address Claim" PG from source address 0xFE) is sent once.

**Note**: It is not possible to claim the broadcast address 0xFF.

## Parameters

- **ecuHandle**: ECU handle
- **newAddress**: address to be claimed or Null Address (0xFE) to go offline

## Return Values

0 on success or [error code](../CAPLfunctionsJ1939NLErrorCodes.md)

## Example

```c
J1939ECUGoOnline(ecuHdl, 0x06);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
