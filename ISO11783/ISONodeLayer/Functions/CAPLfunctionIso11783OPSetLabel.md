[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPSetLabel.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPSetLabel

# Iso11783OPSetLabel

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPSetLabel( dword ecuHandle, dword objectID, 
 dword stringVarIdD, dword fontType, dword graphID );
```

## Description

A **Set Label** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object ID which is assigned to the label
- **stringVarID**: Object ID of the string variable object
- **fontType**: Font type
- **graphID**: Object ID of a graphical object

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPSetLabel( handle, 1200, 1250, 1, 1260 );
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
