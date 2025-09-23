[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSubStrCpyOff.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » substr_cpy_off

# substr_cpy_off

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
void substr_cpy_off(char dest[], long destOffset, char src[], long srcStart, long len, long max);
```

## Description

This function copies a substring of **src** to **dest**. **max** indicates the size of **dest** in bytes. The function ensures that there is a terminating ‘\0’. Thus, a maximum of max-1-destOffset bytes are copied.

**Note:** A character may need several bytes depending on the string encoding, e.g. Japanese characters in Windows ANSI (932) encoding or any special characters in UTF-8 encoding. In that case, you should use [mbsubstr_cpy_off](CAPLfunctionMbSubStrCpy.md) instead.

## Parameters

- **dest**: Destination buffer
- **destOffset**: Offset in bytes in destination buffer
- **src**: Source string
- **srcStart**: Start index in bytes in **src** of substring
- **len**: Length of the substring in bytes, or -1 to copy the string until the end
- **max**: Size of **dest** in bytes

## Return Values

—

## Example

```c
char s1[9] = "New CAPL";
char s2[18] = "Vector Informatik";
substr_cpy_off(s2, 7, s1, 4, -1, elcount(s2)); // s2: Vector CAPL
```

[strstr](CAPLfunctionStrStr.md)
