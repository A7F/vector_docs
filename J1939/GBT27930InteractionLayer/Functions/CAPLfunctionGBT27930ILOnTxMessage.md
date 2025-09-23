[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILOnTxMessage.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GB/T 27930 IL](../CAPLfunctionsGBT27930ILOverview.md) » GBT27930IL_OnTxMessage

# GBT27930IL_OnTxMessage (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void GBT27930IL_OnTxMessage( pg * txPG )
```

## Description

This callback function is called from the GBT27930 IL if a message was sent successfully.

## Parameters

- **txPG**: message which was sent

## Example

```c
//report about the sending of a CRM message (PGN = 0x100)
//with 0xAA in the first byte (BMS is recognized)
void GBT27930IL_OnTxMessage( pg * txPG )
{
  switch( txPG.PGN )
  {
    case 0x600:
      if(txPG.byte(0) == 0xAA)
        writeEx(-3, 3, "CRM (BMS is recognized) is sent");
      break;
  }
}
```
