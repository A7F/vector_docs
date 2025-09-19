[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILOnTxMessage.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_OnTxMessage**

# VTIL_OnTxMessage (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void VTIL_OnTxMessage( pg * txPG );
```

## Description

This callback function is called from the VT IL if a message was sent successfully.

## Parameters

- **txPG**: Message which was sent

## Return Values

—

## Example

```c
void VTIL_OnTxMessage( pg * txPG )
{
  switch( txPG.PGN ) {
    case 0xFF01:
      break;
  }
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
