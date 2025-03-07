[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetBlockedTxTpCts.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_ResetBlockedTxTpCts**

# VTIL_ResetBlockedTxTpCts

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_ResetBlockedTxTpCts( ); // Form 1
long VTIL_ResetBlockedTxTpCts( dbNode node); // Form 2
```

## Description

Resets all CTS messages that were blocked with [VTIL_BlockTxTpCts](CAPLfunctionIso11783VTILBlockTxTpCts.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = VTIL_BlockTxTpCts(1); // Block the first CTS message
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
// Reset blocked TP.CTS messages by pressing ‘a’ on the keyboard.
on key 'a' {
  long res;
  res = VTIL_ResetBlockedTxTpCts(); // Resets all blocked TP.CTS messages.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)