[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AssociativeFields/Functions/CAPLfunctionSize.md)

[CAPL Functions](../../CAPLfunctions.md) » [Associative Fields »](../CAPLfunctionsAssociativeFieldOverview.md) **size**

# size

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax (Dynamic)

- `long map[char[]]::size();`
- `long map[float]::size();`
- `long map[int64]::size();`
- `long map[long]::size();`

## Description

Returns the number of elements in the field.

**Note**: The function [elcount](../../Other/Functions/CAPLfunctionElCount.md) always returns 1 when called with an associative field; it is only meant for non-associative fields (arrays).

## Complexity

O(1)

## Parameters

—

## Return Values

Number of elements in the field.

## Example

```plaintext
if (m.size() == 0) write("Map is empty!");
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)