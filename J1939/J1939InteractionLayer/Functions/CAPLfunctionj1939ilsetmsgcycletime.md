[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionj1939ilsetmsgcycletime.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILSetMsgCycleTime

# J1939ILSetMsgCycleTime

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILSetMsgCycleTime(dbMsg dbMessage, dword cycleTime ); // form 1
long J1939ILSetMsgCycleTime(dbNode node, dbMsg dbMessage, dword cycleTime ); // form 2
```

## Description

Sets the message cycle time in ms.

## Parameters

- **dbMessage**: message name as defined in the database
- **cycleTime**: cycle time in ms
- **node**: Simulation node to apply the function

## Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)