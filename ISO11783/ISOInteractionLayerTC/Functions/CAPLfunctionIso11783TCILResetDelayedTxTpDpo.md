[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILResetDelayedTxTpDpo.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_ResetDelayedTxTpDpo**

# TCIL_ResetDelayedTxTpDpo

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_ResetDelayedTxTpDpo(); //Form 1
long TCIL_ResetDelayedTxTpDpo(dbNode node); //Form 2
```

## Description

Resets all DPO messages that were blocked with [TCIL_DelayTxTpDpo](CAPLfunctionIso11783TCILDelayTxTpDpo.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = TCIL_DelayTxTpDpo(1, 2, 20); // Delay the first two ETP.DPO messages for 20 ms
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
// Reset blocked ETP.DPO messages by pressing ‘a’ on the keyboard.
on key 'a'{
  long res;
  res = TCIL_ResetDelayedTxTpDpo(); // Resets all blocked ETP.DPO messages.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
