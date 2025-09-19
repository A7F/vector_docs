[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionFileClose.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » fileClose

# fileClose

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long fileClose (dword fileHandle);
```

## Method Syntax (Dynamic)

```
long File::Close();
```

## Description

This function closes the specified file.

## Parameters

The integer contains the handle to the file.

## Return Values

If an error occurs the return value is 0, else 1.

## Example

See [File Functions](CAPLfunctionsExapmleFileFunctions.md)

[Class: File](../../ObjectOrientedProg/CAPLfunctionsOOPFile.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
