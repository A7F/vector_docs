[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILResetBlockedTxTpEoma.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_ResetBlockedTxTpEoma

# FSIL_ResetBlockedTxTpEoma

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_ResetBlockedTxTpEoma(); // Form 1
long FSIL_ResetBlockedTxTpEoma(dbNode node); // Form 2
```

## Description

Resets all EoMA messages that were blocked with [FSIL_BlockTxTpEoma](CAPLfunctionIso11783FSILBlockTxTpEoma.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = FSIL_BlockTxTpEoma(1); // Block the TP.EoMA message
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
on key 'a' {
  long res;
  res = FSIL_ResetBlockedTxTpEoma(); // Resets blocked TP.EoMA message.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
