[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILDelayTxTpEoma.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_DelayTxTpEoma

# FSIL_DelayTxTpEoma

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long FSIL_DelayTxTpEoma(long timeout); //Form 1`
- `long FSIL_DelayTxTpEoma(dbNode node, long timeout); //Form 2`

## Description

Delays transmitting of the (E)TP.EoMA (End Of Message Acknowledgment) message generated and sent by the interaction layer. The EoMA message is delayed every time until the CAPL function [FSIL_ILResetDelayedTxTpEoma](CAPLfunctionIso11783FSILResetDelayedTxTpEoma.md) is called.

The delay time is added to the value set by [FSIL_SetNodeProperty("EoMALatency", …)](CAPLfunctionIso11783FSILSetNodeProperty.md).

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
  res = FSIL_DelayTxTpEoma(200); // Delay TP.EoMA by 200 ms.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)