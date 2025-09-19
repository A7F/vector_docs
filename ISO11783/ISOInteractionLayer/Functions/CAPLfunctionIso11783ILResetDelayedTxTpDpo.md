[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILResetDelayedTxTpDpo.md)

**Structure Path:** [CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_ResetDelayedTxTpDpo

# Iso11783IL_ResetDelayedTxTpDpo

**Valid for:** [CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_ResetDelayedTxTpDpo(); //Form 1`
- `long Iso11783IL_ResetDelayedTxTpDpo(dbNode node); //Form 2`

## Description

Resets all DPO messages that were blocked with [ISO11783IL_DelayTxTpDpo](CAPLfunctionIso11783ILDelayTxTpDpo.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = ISO11783IL_DelayTxTpDpo(1, 2, 20); // Delay the first two ETP.DPO messages for 20 ms
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
// Reset blocked ETP.DPO messages by pressing ‘a’ on the keyboard.
on key 'a'{
  long res;
  res = ISO11783IL_ResetDelayedTxTpDpo(); // Resets all blocked ETP.DPO messages.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
