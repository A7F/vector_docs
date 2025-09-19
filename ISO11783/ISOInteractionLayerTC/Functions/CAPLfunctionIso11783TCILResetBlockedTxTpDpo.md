[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILResetBlockedTxTpDpo.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_ResetBlockedTxTpDpo

# TCIL_ResetBlockedTxTpDpo

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_ResetBlockedTxTpDpo(); //Form 1`
- `long TCIL_ResetBlockedTxTpDpo(dbNode node); //Form 2`

## Description

Resets all DPO messages that were blocked with [TCIL_BlockTxTpDpo](CAPLfunctionIso11783TCILBlockTxTpDpo.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = TCIL_BlockTxTpDpo(1); // Block the first ETP.DPO message
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
// Reset blocked ETP.DPO messages by pressing ‘a’ on the keyboard.
on key 'a'{
  long res;
  res = TCIL_ResetBlockedTxTpDpo(); // Resets all blocked ETP.DPO messages.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
