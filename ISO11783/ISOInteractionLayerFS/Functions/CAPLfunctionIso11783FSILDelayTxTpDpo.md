[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILDelayTxTpDpo.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_DelayTxTpDpo**

# FSIL_DelayTxTpDpo

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_DelayTxTpDpo(long dpoToBlock); //Form 1
long FSIL_DelayTxTpDpo(dbNode node, long dpoToBlock); //Form 2
```

## Description

Delays transmitting of a ETP.DPO message generated and sent by the interaction layer. The message to be delayed is identified by its occurrences on the bus, starting at 1. The given DPO message is delayed every time until the CAPL function [FSIL_ResetDelayedTxTpDpo](CAPLfunctionIso11783FSILResetDelayedTxTpDpo.md) is called.

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
  res = FSIL_DelayTxTpDpo(1); // Block the first ETP.DPO message
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)