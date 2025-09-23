[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783AppErrorIndication.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783AppErrorIndication

# Iso11783AppErrorIndication (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword Iso11783AppErrorIndication( long ecuHandle, long errorClass, long errorNumber, long addCode );
```

## Description

Indicates that errors have occurred during a transfer or else during the initialization of ECUs (for example timeout during the transport protocol). If an Address Claiming procedure has failed, that will also be reported by means of this function.

## Parameters

- **ecuHandle**: ECU handle
- **errorClass**: Error class
- **errorNumber**: Error number
- **addCode**: Additional error parameter, depends on the error number (i.e. the PGN)

## Return Values

—

## Example

```plaintext
dword Iso11783AppErrorIndication( 
 LONG ecuHdl, LONG errClass, LONG errNum, LONG addCode )
{
  /* user code */
  return 0;
}
```
