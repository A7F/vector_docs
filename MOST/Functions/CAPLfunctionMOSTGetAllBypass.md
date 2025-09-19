[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetAllBypass.md)

**CAPL Functions** » **MOST** » **mostGetAllBypass**

# mostGetAllBypass

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostGetAllBypass(long channel);
```

## Description

Return indicates whether the MOST hardware bypass is closed (Return value = 1) or open (Return value = 0).

## Parameters

- **channel**: Channel of the connected hardware.

## Return Values

- **0**: Bypass is opened
- **1**: Bypass is closed
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—
