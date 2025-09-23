[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILDelayTxTpEoma.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_DelayTxTpEoma**

# TCIL_DelayTxTpEoma

[Valid for: CANoe DE • CANoe4SW DE](../../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long TCIL_DelayTxTpEoma(long timeout); //Form 1
long TCIL_DelayTxTpEoma(dbNode node, long timeout); //Form 2
```

## Description

Delays transmitting of the (E)TP.EoMA (End Of Message Acknowledgment) message generated and sent by the interaction layer. The EoMA message is delayed every time until the CAPL function [TCIL_ILResetDelayedTxTpEoma](CAPLfunctionIso11783TCILResetDelayedTxTpEoma.md) is called.

The delay time is added to the value set by [TCIL_SetNodeProperty("EoMALatency", …)](CAPLfunctionIso11783TCILSetNodeProperty.md).

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
  res = TCIL_DelayTxTpEoma(200); // Delay TP.EoMA by 200 ms.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```
