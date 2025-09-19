[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILResetAllDelayedRxMessage.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_ResetAllDelayedRxMessage

# FSIL_ResetAllDelayedRxMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long FSIL_ResetAllDelayedRxMessage(dword behavior); // form 1`
- `long FSIL_ResetAllDelayedRxMessage(dbNode node, dword behavior); // form 2`

## Description

Resets the change of all [FSIL_DelayRxMessage](CAPLfunctionIso11783FSILDelayRxMessage.md) calls.

## Parameters

- **behavior**
  - 0: Do not process currently delayed messages
  - 1: Process currently delayed messages after the defined delay

- **node**
  - Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **-102**: An invalid parameter is used

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
