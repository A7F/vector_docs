# GPIBGetIntResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long GPIBGetIntResult (char[] buffer);
```

## Description

Helper functions for extracting numeric values from GPIB response strings.

## Parameters

- **buffer**: The string in buffer, which may have been obtained by the [GPIBResponse](CAPLfunctionGPIBResponse.md) function, is searched for an integer number: All non-digit characters in the string as well as all digits found after the first comma character or decimal point are ignored, when assembling the integer number.

## Return Values

Extracted integer value.

## Example

—
