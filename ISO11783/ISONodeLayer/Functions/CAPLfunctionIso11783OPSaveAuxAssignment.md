[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPSaveAuxAssignment.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPSaveAuxAssignment

# Iso11783OPSaveAuxAssignment

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPSaveAuxAssignment( dword ecuHandle, char filename[] );
```

## Description

The function saves the current auxiliary input assignment as "Preferred Auxiliary Input Assignment" in an ini file.

With the function [Iso11783OPLoadAuxAssignment](CAPLfunctionIso11783OPLoadAuxAssignment.md) the "Preferred Assignment" can be load and used again.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).
- **filename**: Filename of an ini file (*.INI)

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
dword handle = 0;
handle = Iso11783CreateECU( gECUName );
[...]
Iso11783OPSaveAuxAssignment( handle, "Sprayer.INI");
[...]
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
