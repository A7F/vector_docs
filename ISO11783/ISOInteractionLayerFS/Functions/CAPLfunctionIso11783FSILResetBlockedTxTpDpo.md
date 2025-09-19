[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILResetBlockedTxTpDpo.md)

## FSIL_ResetBlockedTxTpDpo

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_ResetBlockedTxTpDpo

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
long FSIL_ResetBlockedTxTpDpo(); //Form 1
long FSIL_ResetBlockedTxTpDpo(dbNode node); //Form 2
```

### Description

Resets all DPO messages that were blocked with [FSIL_BlockTxTpDpo](CAPLfunctionIso11783FSILBlockTxTpDpo.md).

### Parameters

- **node**: Simulation node to apply the function.

### Return Values

- **0**: OK
- **-1**: General Error

### Example

```plaintext
on start {
  long res;
  res = FSIL_BlockTxTpDpo(1); // Block the first ETP.DPO message
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
// Reset blocked ETP.DPO messages by pressing ‘a’ on the keyboard.
on key 'a'{
  long res;
  res = FSIL_ResetBlockedTxTpDpo(); // Resets all blocked ETP.DPO messages.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
