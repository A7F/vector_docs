[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILDelayTxTpAbort.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_DelayTxTpAbort

# TCIL_DelayTxTpAbort

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_DelayTxTpAbort(long timeout); //Form 1`
- `long TCIL_DelayTxTpAbort(dbNode node, long timeout); //Form 2`

## Description

Delays transmitting of the (E)TP.Abort message generated and sent by the interaction layer. The Abort message is delayed every time until the CAPL function [TCIL_ResetDelayedTxTpAbort](CAPLfunctionIso11783TCILResetDelayededTxTpAbort.md) is called.

The delay time is added to the value set by [TCIL_SetNodeProperty("AbortLatency", …)](CAPLfunctionIso11783TCILSetNodeProperty.md).

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
  res = TCIL_DelayTxTpAbort(200); // Delay TP.Abort by 200ms.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
