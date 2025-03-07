[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILDelayTxTpDpo.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_DelayTxTpDpo

# VTIL_DelayTxTpDpo

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_DelayTxTpDpo(long dpoToBlock);` //Form 1
- `long VTIL_DelayTxTpDpo(dbNode node, long dpoToBlock);` //Form 2

## Description

Delays transmitting of a ETP.DPO message generated and sent by the interaction layer. The message to be delayed is identified by its occurrences on the bus, starting at 1. The given DPO message is delayed every time until the CAPL function [VTIL_ResetDelayedTxTpDpo](CAPLfunctionIso11783VTILResetDelayedTxTpDpo.md) is called.

## Parameters

- **dpoToBlock**: The ETP.DPO message that shall be blocked.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error
- **-3002**: Parameter **dpoToBlock** must be greater than 0

## Example

```plaintext
on start {
  long res;
  res = VTIL_DelayTxTpDpo(1); // Block the first ETP.DPO message
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)