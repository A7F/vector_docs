[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionMbStrLen.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » mbstrlen

# mbstrlen

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long mbstrlen(char s[]);
```

## Description

The functional result is the length of the string **s** in **characters**.

## Parameters

**string**

## Return Values

Length of the string in characters.

## Example

```plaintext
long length;
char s1[10] = "door";
char s2[10] = "Tür";
write("%d %d", mbstrlen(s1), strlen(s1)); // 4 4
write("%d %d", mbstrlen(s2), strlen(s2)); // 3 [3 or 4 depending on file encoding]
```

[strlen](CAPLfunctionStrLen.md) • [mbstrncmp](CAPLfunctionMbStrnCmp.md) • [mbstrncpy](CAPLfunctionMbStrnCpy.md)
