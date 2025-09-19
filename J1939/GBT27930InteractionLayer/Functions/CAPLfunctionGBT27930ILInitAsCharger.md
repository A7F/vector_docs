[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILInitAsCharger.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GB/T 27930 IL](../CAPLfunctionsGBT27930ILOverview.md) » GBT27930IL_InitAsCharger

# GBT27930IL_InitAsCharger

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_InitAsCharger(); // form 1`
- `long GBT27930IL_InitAsCharger(dbNode node); // form 2`

## Description

Inits simulated node as a charger. This function may be called at the earliest in **on start**, then it is verified whether all necessary messages are entered into the Tx list. Info about all missing messages will be displayed in the Write Window.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: on success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
