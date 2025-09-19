[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939GetWSMaster.md)

# J1939GetWSMaster

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939GetWSMaster

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939GetWSMaster(char busName[], dword ecuAddress)
```

## Description

This function returns the address of the Working Set Master, which is assigned to an ECU with the address `ecuAddress`.

## Parameters

- **busName**: name of the bus
- **ecuAddress**: address of an ECU

## Return Values

Address of the Working Set Master

## Example

```c
wsmAddr = J1939GetWSMaster("default", 10);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
