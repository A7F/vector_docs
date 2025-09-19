[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStrnCpy.md)

**CAPL Functions** » **General** » **Function Overview** » **strncpy**

# strncpy

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
void strncpy(char dest[], char src[], long max);
```

## Description

This function copies **src** to **dest**. **max** indicates the size of **dest** in bytes. The function ensures that there is a terminating '\0'. Thus, a maximum of **max-1** bytes are copied.

**Note:** A character may need several bytes depending on the string encoding, e.g. Japanese characters in Windows ANSI (932) encoding or any special characters in UTF-8 encoding. In that case, you should use [mbstrncpy](CAPLfunctionMbStrnCpy.md) instead.

## Parameters

- **dest**: Destination buffer
- **src**: Source string
- **max**: Is used to determine the maximum number of copied bytes. Must not be larger than the size of **dest**. A maximum of **max-1** bytes are copied. If **src** is shorter than that, bytes are only copied until a terminating '\0' is encountered.

## Return Values

—

## Example

```c
variables {
    char s1[7] = "Vector";
    char s2 [32];
}
on key 'z'
{
    strncpy (s2,s1,elcount(s2));
    write ("Result: %s",s2);  // Result: Vector
}
```

[**strlen**](CAPLfunctionStrLen.md) • [**strncat**](CAPLfunctionStrnCat.md) • [**strncmp**](CAPLfunctionStrnCmp.md) • [**strncpy_off**](CAPLfunctionStrnCpyOff.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
