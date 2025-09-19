[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/Functions/CAPLfunctionGPIBGetFloatResult.md)

**CAPL Functions** » **GPIB** » **GPIBGetFloatResult**

# GPIBGetFloatResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
double GPIBGetFloatResult (char[] buffer);
```

## Description

Helper functions for extracting numeric values from GPIB response strings.

## Parameters

- **buffer**: The string in buffer, which may have been obtained by the [GPIBResponse](CAPLfunctionGPIBResponse.md) function, is searched for a floating-point number, using the function `strtod` of C/C++. If a space character is present in the string, the search for the number starts at the first such character.

## Return Values

- **Extracted float value**

- **0**: No representation of a value has been found.

- **-1**: **buffer** is an empty string.

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
