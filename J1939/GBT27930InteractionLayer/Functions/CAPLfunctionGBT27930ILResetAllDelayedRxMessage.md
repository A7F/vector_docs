[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILResetAllDelayedRxMessage.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GB/T 27930 IL](../CAPLfunctionsGBT27930ILOverview.md) » GBT27930IL_ResetAllDelayedRxMessage

# GBT27930IL_ResetAllDelayedRxMessage

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_ResetAllDelayedRxMessage(dword behavior);` // form 1
- `long GBT27930IL_ResetAllDelayedRxMessage(dbNode node, dword behavior);` // form 2

## Description

Resets the change of all [GBT27930IL_DelayRxMessage](CAPLfunctionGBT27930ILDelayRxMessage.md) calls.

## Parameters

- **behavior**
  - 0: Do not process currently delayed messages
  - 1: Process currently delayed messages after the defined delay

- **node**
  - Simulation node to apply the function.

## Return Values

- **0**
  - Function has been executed successfully

- **-102**
  - An invalid parameter is used

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)