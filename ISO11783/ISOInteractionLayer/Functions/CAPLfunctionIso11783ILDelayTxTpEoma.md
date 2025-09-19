[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILDelayTxTpEoma.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_DelayTxTpEoma

# Iso11783IL_DelayTxTpEoma

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_DelayTxTpEoma(long timeout); //Form 1`
- `long Iso11783IL_DelayTxTpEoma(dbNode node, long timeout); //Form 2`

## Description

Delays transmitting of the (E)TP.EoMA (End Of Message Acknowledgement) message generated and sent by the interaction layer. The EoMA message is delayed every time until the CAPL function [Iso11783IL_ILResetDelayedTxTpEoma](CAPLfunctionIso11783ILResetDelayedTxTpEoma.md) is called.

The delay time is added to the value set by [Iso11783IL_SetNodeProperty("EoMALatency", …)](CAPLfunctionIso11783ILSetNodeProperty.md).

## Parameters

- **timeout**: Delay in milliseconds [1…3600000].
- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error
- **-3004**: Parameter **timeout** must be greater than 0

## Example

```plaintext
on start {
  long res;
  res = Iso11783IL_DelayTxTpEoma(200); // Delay TP.EoMA by 200 ms.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
