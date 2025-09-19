[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILOnTxPrepare.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_OnTxPrepare**

# GBT27930IL_OnTxPrepare (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_OnTxPrepare( pg * txPG )
```

## Description

This callback function is called from the GBT27930 IL before a parameter group is sent. The signal value can be updated in the callback or sending of the message can be suppressed.

## Parameters

- **txPG**: message which should be sent

## Return Values

- **1**: send message
- **0**: do not send message

## Example

```plaintext
//Block the CRM message (PGN = 0x0100) if the first byte is 0x00
//Modify the BCL message (PGN = 0x1000):
//  switch the charging mode from "constant current" to "constant voltage"
long GBT27930IL_OnTxPrepare( pg * txPG )
{
  int retValue = 1;
  switch( txPG.PGN )
  {
    case 0x0100:
      if(txPG.byte(0) == 0x9)
        retValue = 0;
      break;
    case 0x1000:
      if(txPG.byte(4) == 0x2)
        txPG.byte(4) = 0x1;
      break;
  }
  return retValue;
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
