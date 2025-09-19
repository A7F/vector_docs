[J1939ILOnTxPrepare](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILOnTxPrepare.md) (Callback)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILOnTxPrepare

### Function Syntax

```plaintext
long J1939ILOnTxPrepare( pg * txPG )
```

### Description

This callback function is called from the J1939 IL before a parameter group is sent. The signal value can be updated in the callback or sending of the message can be suppressed.

**Note Suppressing of AddressClaim and CannotClaimAddress Messages.**

Using this method you can suppress the **AddressClaim** or **CannotClaimAddress** messages as well. Please notify that in this case the corresponding node will switch to the [next state](../../../../CANoeCANalyzer/J1939/j1939IL/j1939ILStates.md) (Active, Stopped or Initialized) even though the **AddressClaim** or **CannotClaimAddress** message has been not sent.

You can use this method for the delaying of the **AddressClaim** message. Just suppress the **AddressClaim** message by the J1939 IL and send it some milliseconds later by the CAPL program.

### Parameters

- **txPG**: message which should be sent

### Return Values

- **1**: send message
- **0**: do not send message

### Example

```plaintext
long J1939ILOnTxPrepare( pg * txPG )
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

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
