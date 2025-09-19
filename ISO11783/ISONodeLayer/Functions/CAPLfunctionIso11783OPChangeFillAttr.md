[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPChangeFillAttr.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPChangeFillAttribute

# Iso11783OPChangeFillAttribute

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangeFillAttribute( dword ecuHandle, dword objectID, dword color, dword type, dword patternID );
```

## Description

The function changes the properties of a fill attribute object. A **Change Fill Attribute** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object ID of a fill attribute object
- **color**: Color index
- **type**: Fill type:
  - 0: do not fill
  - 1: fill with line color
  - 2: fill with fill color
  - 3: fill with pattern from patternID
- **patternID**: Object ID of a picture object, which is used as fill pattern

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPChangeFillAttribute( handle, 1100, 12, 2, 0xFFFF );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
