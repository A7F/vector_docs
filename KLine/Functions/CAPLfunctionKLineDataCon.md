[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineDataCon.md)

**CAPL Functions** » **K-Line** » _KLine_DataCon

# _KLine_DataCon

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

_KLine_DataCon(long count)

## Description

Called for a transmitted K-Line response.

**Note**

This function models a K-Line TP layer which is required for an ECU simulation.

## Parameters

- **count**: Number of transmitted bytes.

## Return Values

—

## Example

```c
_KLine_DataCon( long count)
{
   write("%d byte sent", count);
   diag_DataCon( count);
}
```

[_KLine_DataInd](CAPLfunctionKLineDataInd.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)