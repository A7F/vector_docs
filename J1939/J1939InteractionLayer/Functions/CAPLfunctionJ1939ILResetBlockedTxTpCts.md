[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILResetBlockedTxTpCts.md)

## J1939ILResetBlockedTxTpCts

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILResetBlockedTxTpCts

### Tool Availability
[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Function Syntax

- `long J1939ILResetBlockedTxTpCts();` //Form 1
- `long J1939ILResetBlockedTxTpCts(dbNode node);` //Form 2

### Description

Resets all CTS messages that were blocked with [J1939ILBlockTxTpCts](CAPLfunctionJ1939ILBlockTxTpCts.md).

### Parameters

- **node**: Simulation node to apply the function.

### Return Values

- **0**: OK
- **-1**: General Error

### Example

```plaintext
on start {
  long res;
  res = J1939ILBlockTxTpCts(1); // Block the first CTS message
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
// Reset blocked TP.CTS messages by pressing ‘a’ on the keyboard.
on key 'a'{
  long res;
  res = J1939ILResetBlockedTxTpCts(); // Resets all blocked TP.CTS messages.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
