[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionWrite.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » write

# write

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void write(char format[], ...);
```

## Description

Outputs a text message to the Write Window. Write is based on the C function `printf`.

The compiler cannot check the format string. Illegal format entries will lead to undefined results. Messages output with the write function will be displayed on separate lines.

## Parameters

Format string, variables or [expressions](../CAPLFunctionsWriteFormatExpressions.md)

## Return Values

—

## Example

Examples:

```plaintext
float f=123.456;
on key 'h'
{
   write("Hello World!");
   write("f = %5.3f",f);
   write("format is not supported for the given variable");
   write("f = %7.3f",f);
   write("f = %9.3f",f);
}
```

```plaintext
on key 'q'
{
   qword q = 0x1234567890ABCDEFLL;
   write("Decimal: %I64u", q);
   write("Hexadecimal: %I64X", q);
}
```

```plaintext
on key 'd'
{
   dword d = 0x1234;
   write("Decimal: %u", d);
   write("Hexadecimal: %X", d);
}
```

[snprintf](CAPLfunctionSnPrintf.md) • [writeToLog](CAPLfunctionWriteToLog.md) • [writeToLogEx](CAPLfunctionWriteToLogEx.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
