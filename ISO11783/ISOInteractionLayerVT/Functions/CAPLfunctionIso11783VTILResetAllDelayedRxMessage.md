[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetAllDelayedRxMessage.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_ResetAllDelayedRxMessage

# VTIL_ResetAllDelayedRxMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_ResetAllDelayedRxMessage(dword behavior); // form 1`
- `long VTIL_ResetAllDelayedRxMessage(dbNode node, dword behavior); // form 2`

## Description

Resets the change of all [VTIL_DelayRxMessage](CAPLfunctionIso11783VTILDelayRxMessage.md) calls.

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

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)