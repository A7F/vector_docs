[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSapperrorindication.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSAppErrorIndication**

# GNSSAppErrorIndication

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void GNSSAppErrorIndication( long errNum, long errClass, long addInfo )
```

## Description

This function identifies errors that occurred during a transfer or else during the initialization of the node (for example timeout during the transport protocol). If an Address Claiming procedure has failed, that will also be reported by means of this function.

The error classes and error codes are described [here](../CAPLfunctionsGNSSNLErrorCodesAppErrorIndication.md).

## Parameters

- **errNum**: Error number
- **errClass**: Error class
- **addInfo**: Additional error information

## Return Values

—

## Example

```plaintext
void GNSSAppErrorIndication( LONG errorClass, LONG errorCode, LONG addInfo )
{
  write( "Error code = %d",errCode);
}
```
