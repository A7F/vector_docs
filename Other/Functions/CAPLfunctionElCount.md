[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionElCount.md)

**CAPL Functions** » **General** » **Function Overview** » **elCount**

# elCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long elcount(...);` // if used with arrays which are function parameters
- `dword elcount(...);` // in all other cases

## Description

Determines the number of elements of an array.

**Note**: The function `elcount` always returns 1 when called with an associative field; it is only meant for non-associative fields (arrays).

## Parameters

Array of any arbitrary type.

## Return Values

Number of elements.

## Example

```c
void bsp(int ar[]) {
    int i;
    for(i=0; i < elCount(ar); i++)
        ...
}

void bsp2(byte ar[][]) {
    int i, j;
    for(j=0; j < elCount(ar); j++ )
        for(i=0; i <= elCount(ar[j]); i++ )
            ...
}
```

[runError](CAPLfunctionRunError.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
