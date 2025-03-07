[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AssociativeFields/Functions/CAPLfunctionRemove.md)

[CAPL Functions](../../CAPLfunctions.md) » [Associative Fields »](../CAPLfunctionsAssociativeFieldOverview.md) remove

# remove

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax (Dynamic)

- `long map[char[]]::remove(char key[]);`
- `long map[float]::remove(float key);`
- `long map[int64]::remove(int64 key);`
- `long map[long]::remove(long key);`

## Description

Removes one element from the field.

## Complexity

O(log(N))

## Parameters

- **key**: Key of the element.

## Return Values

- **1**: Key was available
- **0**: Key was not available

## Example

```plaintext
m.remove(3);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)