[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILBlockTxTpDt.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_BlockTxTpDt

# Iso11783IL_BlockTxTpDt

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_BlockTxTpDt( long firstMsg, long numOfMsg, long timeout); //Form 1
long Iso11783IL_BlockTxTpDt( dbNode node, long firstMsg, long numOfMsg, long timeout); //Form 2
```

## Description

Prevents transmitting of (E)TP.DT messages generated and sent by the interaction layer. The messages to be blocked are identified by their occurrences on the bus, starting at 1 until the given message count is reached. The given range of DT messages are blocked every time until the CAPL function [Iso11783IL_ResetBlockedTxTpDt](CAPLfunctionIso11783ILResetBlockedTxTpDt.md) is called. After blocking the DT messages, the Interaction Layer continues as if no error occurred. The timeout parameter specifies whether the ongoing messages shall be sent immediately or after the given time in milliseconds passed.

## Parameters

- **firstMsg**: The sequence number of the first DT message that shall be blocked [1…n].
- **numOfMsg**: Number of DT messages that shall be blocked [1…n].
- **timeout**: The delay in milliseconds to continue the transmission with regularly sent DT messages.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error
- **-3002**: Parameter **firstMsg** must be greater than 0
- **-3003**: Parameter **numOfMsg** must be greater than 0

## Example

```plaintext
on start {
  long res;
  // Block TP.DT packets 6, 7, 8, 9. Continue with packet no. 10 without delay.
  res = Iso11783IL_BlockTxTpDt(6, 4, 0);
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
