[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILOnCA.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_OnCA

# TCIL_OnCA (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_OnCA(long newAddress);
```

## Description

This callback function is called from the TC IL when a Command Address message is received.

The return value defines the node reaction to the Command Address message (the assignment of the new address can be suppressed).

## Parameters

- **newAddress**
  - 0..253: new address that ECU can accept
  - 254: ECU has to go offline

## Return Values

- **1**: Accept the new address
- **0**: Don’t accept the new address

## Example

```plaintext
long TCIL_OnCA(long address)
{
  if(address == 2)
    return 0; // don’t accept the address ‘2’
  else
    return 1;
}
```
