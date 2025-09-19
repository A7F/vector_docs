[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILDelayTxTpDpo.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_DelayTxTpDpo

# Iso11783IL_DelayTxTpDpo

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_DelayTxTpDpo(long dpoToBlock); //Form 1`
- `long Iso11783IL_DelayTxTpDpo(dbNode node, long dpoToBlock); //Form 2`

## Description

Delays transmitting of a ETP.DPO message generated and sent by the interaction layer. The message to be delayed is identified by its occurrences on the bus, starting at 1. The given DPO message is delayed every time until the CAPL function [ISO11783IL_ResetDelayedTxTpDpo](CAPLfunctionIso11783ILResetDelayedTxTpDpo.md) is called.

## Parameters

- **dpoToBlock**: The ETP.DPO message that shall be blocked.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error
- **-3002**: Parameter **dpoToBlock** must be greater than 0

## Example

```plaintext
on start {
  long res;
  res = Iso11783IL_DelayTxTpDpo(1); // Block the first ETP.DPO message
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
