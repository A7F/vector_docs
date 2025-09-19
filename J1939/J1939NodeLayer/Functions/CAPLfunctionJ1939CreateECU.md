[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939CreateECU.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939CreateECU

# J1939CreateECU

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword J1939CreateECU( dword busHandle, char deviceName[] );
dword J1939CreateECU( char busName[], char deviceName[] );
```

## Description

This function sets up a logical node within a CANoe network node. Several logical nodes can be generated for each CANoe network node. At least one logical node must be generated for each CANoe network node.

The `deviceName` parameter is used to transfer the device name (see J1939 naming convention) of the logical node.

With the parameter `busName`, you must select a bus on which this ECU will be used. Care should be taken not to assign any name twice on one network (J1939 specification). It is allowed to assign an ECU name twice, if another bus is used. On this way a gateway capability can be reached. The joint handling of these instances shall be tasked by the application. Only buses can be used, which are assigned in the Simulation Setup. If the node is assigned only to one bus, the `busname` "default" can be used.

The handle serves as an unique key to the generated ECU and must therefore be saved for as long as the logical node is in use.

## Parameters

- **busHandle**: current bus handle
- **deviceName**: 64-bit device name
- **busName**: bus name (or use "default")

## Return Values

Handle to the generated (logical) ECU or 0 if an error occurred

## Example

```plaintext
ecuHdl = J1939CreateECU( "default", name);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
