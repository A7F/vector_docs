[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStrnCat.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » strncat

# strncat

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
void strncat(char dest[], char src[], long len);
```

## Description

This function appends **src** to **dest**. **len** indicates the maximum length of the composite string. The function ensures that there is a terminating "\0". Thus, a maximum of **len - strlen(dest) - 1** characters are copied.

**Note**: Unlike the `strncat` C-function, rather than the number of characters to be appended, **len** indicates the maximum length of the composite string, including the terminating "\0".

## Parameters

- **dest**: Target string to which characters are appended.
- **src**: Appended string.
- **len**: Maximum length of composite string including terminating '\0'.

## Return Values

—

## Example

```c
char s[20];
strncpy(s, "Vector", 10); // s is "Vector"
strncat(s, " CANoe", 19); // s is "Vector CANoe"
strncpy(s, "Vector", 10); // s is "Vector"
strncat(s, " CANoe", 11); // s is "Vector CAN"
```

[Related Functions: strlen](CAPLfunctionStrLen.md) • [strncmp](CAPLfunctionStrnCmp.md) • [strncpy](CAPLfunctionStrnCpy.md)
