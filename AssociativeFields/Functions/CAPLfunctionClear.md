[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AssociativeFields/Functions/CAPLfunctionClear.md)

**CAPL Functions** » [Associative Fields »](../CAPLfunctionsAssociativeFieldOverview.md) clear

# clear

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax (Dynamic)

- `void map[char[]]::clear();`
- `void map[float]::clear();`
- `void map[int64]::clear();`
- `void map[long]::clear();`

## Description

Removes all elements from the field.

## Complexity

O(log(N) + N)

## Parameters

—

## Return Values

—

## Example

```cpp
m.clear();
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)