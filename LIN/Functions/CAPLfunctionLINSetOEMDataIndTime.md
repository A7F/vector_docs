[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetOEMDataIndTime.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetOEMDataIndTime

# linSetOEMDataIndTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function can be used for OEM specific variant of LIN protocol only.

## Function Syntax

```plaintext
long linSetOEMDataIndTime(long timeInMS);
```

## Description

Sets the time in milliseconds after which a simulated slave automatically sets its data indication bit.

## Parameters

- **timeInMS**  
  Time value.  
  Unit: milliseconds

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linSetOEMDataInd](CAPLfunctionLINSetOEMDataInd.md) • [linGetOEMDataInd](CAPLfunctionLINGetOEMDataInd.md) • [linCheckOEMDataInd](CAPLfunctionLINCheckOEMDataInd.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
