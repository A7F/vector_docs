[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ilsetmsgdelaytime.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_SetMsgDelayTime**

# GBT27930IL_SetMsgDelayTime

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_SetMsgDelayTime(dbMsg dbMessage, dword delayTime ); // form 1
long GBT27930IL_SetMsgDelayTime(dbNode node, dbMsg dbMessage, dword delayTime ); // form 2
```

## Description

Sets the message delay time in ms.

## Parameters

- **dbMessage**: message name as defined in the database
- **delayTime**: delay time in ms
- **node**: Simulation node to apply the function

## Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
