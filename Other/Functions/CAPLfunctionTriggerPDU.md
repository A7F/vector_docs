[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionTriggerPDU.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » triggerPDU

# triggerPDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void triggerPDU(pdu myPDU);
```

## Description

Triggers a PDU to be sent. If the PDU has an update bit it will be set. After the PDU was sent the update bit will be reset.

## Parameters

Variable of type PDU.

## Return Values

—

## Example

```plaintext
on timer cyclic100ms
{
  PDU randomPDU myPDU;
  myPDU.signal1 = 10;
  myPDU.signal2 = 20;
  triggerPDU(myPDU);
}
```
