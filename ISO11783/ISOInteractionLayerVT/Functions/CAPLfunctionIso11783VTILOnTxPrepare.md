[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILOnTxPrepare.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_OnTxPrepare

# VTIL_OnTxPrepare (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_OnTxPrepare( pg * txPG );
```

## Description

This callback function is called from the VT IL before a parameter group is sent. The signal value can be updated in the callback or sending of the message can be suppressed.

**Note Suppressing of AddressClaim and CannotClaimAddress Messages**

Using this method you can suppress the **AddressClaim** or **CannotClaimAddress** messages as well. Please notify that in this case the corresponding node will switch to the next state (Active, Stopped or Initialized) even though the **AddressClaim** or **CannotClaimAddress** message has been not sent.

You can use this method for the delaying of the **AddressClaim** message. Just suppress the **AddressClaim** message by the ISO11783 IL and send it some milliseconds later by the CAPL program.

## Parameters

- **txPG**: Message which should be sent

## Return Values

- **1**: Send message
- **0**: Do not send message

## Example

```plaintext
long VTIL_OnTxPrepare( pg * txPG )
{
  switch( txPG.PGN ) {
    case 0xFF01:
      txPG.BYTE(0) = 10; // update first byte
      break;
  }
  return 1;
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)