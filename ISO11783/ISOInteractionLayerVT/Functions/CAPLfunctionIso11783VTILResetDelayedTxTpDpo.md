[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetDelayedTxTpDpo.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_ResetDelayedTxTpDpo

# VTIL_ResetDelayedTxTpDpo

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_ResetDelayedTxTpDpo(); //Form 1
long VTIL_ResetDelayedTxTpDpo( dbNode node); //Form 2
```

## Description

Resets all DPO messages that were blocked with [VTIL_DelayTxTpDpo](CAPLfunctionIso11783VTILDelayTxTpDpo.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = VTIL_DelayTxTpDpo(1, 2, 20); // Delay the first two ETP.DPO messages for 20 ms
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
// Reset blocked ETP.DPO messages by pressing ‘a’ on the keyboard.
on key 'a'{
  long res;
  res = VTIL_ResetDelayedTxTpDpo(); // Resets all blocked ETP.DPO messages.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)