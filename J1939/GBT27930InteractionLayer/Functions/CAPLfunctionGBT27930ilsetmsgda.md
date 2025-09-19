[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ilsetmsgda.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » GBT27930IL_SetMsgDA

# GBT27930IL_SetMsgDA

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_SetMsgDA(dbMsg dbMessage, dword destinationAddress ); // form 1
long GBT27930IL_SetMsgDA(dbNode node, dbMsg dbMessage, dword destinationAddress ); // form 2
```

## Description

Sets the message destination address.

## Parameters

- **dbMessage**: message name as defined in the database
- **destinationAddress**: destination address of the message
- **node**: Simulation node to apply the function

## Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
