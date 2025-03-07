[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AssociativeFields/Functions/CAPLfunctionContainsKey.md)

# containsKey

[CAPL Functions](../../CAPLfunctions.md) » [Associative Fields »](../CAPLfunctionsAssociativeFieldOverview.md) containsKey

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax (Dynamic)

- `dword map[char[]]::containsKey(char key[]);`
- `dword map[float]::containsKey(float key);`
- `dword map[int64]::containsKey(int64 key):`
- `dword map[long]::containsKey(long key);`

## Description

Returns the information if a key is available in the field.

## Complexity

O(log(N))

## Parameters

- **key**: Key that should be checked.

## Return Values

- **1**: Key was available
- **0**: Key was not available

## Example

```plaintext
if (m.containsKey(3)) { // ...
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)