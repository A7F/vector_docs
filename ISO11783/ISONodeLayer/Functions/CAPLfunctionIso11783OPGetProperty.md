[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPGetProperty.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPGetProperty

# Iso11783OPGetProperty

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPGetProperty( dword ecuHandle, char propertyName[] );
```

## Description

Returns a property of the Object Pool API, e.g. the supported VT version.

## Parameters

- **ecuHandle**  
  Handle of the ECU.  
  The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).

- **propertyName**  
  Key of the information:
  - "Version" VT version support 2..4, Default 3
  - "DebugLevel" Controls the output to the Write Window
    - 0: No output
    - 1: Only errors
    - 2: Warnings and errors
    - 3: Information, warnings and errors

## Return Values

- **≥ 0**  
  value

- **< 0**  
  an error has occurred, see [error codes](../CAPLfunctionsISONLErrorCodes.md)

- **-102**  
  invalid parameter

- **-1113**  
  unknown property

## Example

```plaintext
LONG version;
version = Iso11783OPGetProperty( handle, "Version" );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
