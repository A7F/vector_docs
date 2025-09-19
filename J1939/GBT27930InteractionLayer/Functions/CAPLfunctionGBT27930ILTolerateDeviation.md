[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILTolerateDeviation.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » GBT27930IL_TolerateDeviation

# GBT27930IL_TolerateDeviation

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_TolerateDeviation (long dlcDeviation, long counterpartAddressDeviation); // (form 1)
long GBT27930IL_TolerateDeviation (dbNode node, long dlcDeviation, long counterpartAddressDeviation); // (form 2)
```

## Description

Allows the simulated node to tolerate variations in the address of the other participant and the length of its messages.

## Parameters

- **dlcDeviation**
  - 0: simulated nodes must not tolerate any deviation in the length of the messages of the other participant
  - 1: simulated node must tolerate deviations in the length of messages of the other participant.

- **counterpartAddressDeviation**
  - 0: simulated nodes must not tolerate any deviation in the address of the other participant
  - 1: simulated node must tolerate deviations in the address of the other participant.

- **node**
  - Simulation node to apply the function

## Return Values

- **0**
  - on success

- **< 0**
  - [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example: —

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
