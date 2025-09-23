[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPOnIdentifyWorkingSet.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPOnIdentifyWorkingSet

# Iso11783OPOnIdentifyWorkingSet (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPOnIdentifyWorkingSet( dword handle );
```

## Description

The function is called by the ISO11783 node layer to determine if the node layer is responsible for sending the Working Set Master message during the object pool initialization (after the VT status message appears).

If this callback function is not implemented or it returns the value 1, the Working Set Master message is sent by the ISO11783 node layer. The transmitted number of Working Set members is 1. If the return value of the function is 0, the ISO11783 node layer doesn’t send the Working Set Master message. Instead, the CAPL application sends the Working Set Master message.

## Parameters

- **ecuHandle**: Handle of the ECU

## Return Values

- **1**: Working Set Master message is sent by the ISO11783 node layer with member count 1
- **0**: Working Set Master message is sent by the CAPL application

## Example

```plaintext
LONG Iso11783OPOnIdentifyWorkingSet( dword handle )
{
  return 1;
}
```
