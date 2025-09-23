[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/CAPLfunctionsRuntimeError.md)

## Runtime Errors

[CAPL Functions](../CAPLfunctions.md) » [General](CAPLGeneralStartPage.md) » Runtime Errors

**Valid for:** CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

A number of runtime errors are monitored:

- Division by zero
- Exceeding upper or lower limits of the array
- Exceeding upper or lower limits of offset in the data range of messages.
- Stack overflow when CAPL subroutines are called.

If a runtime error is detected the function [runError](Functions/CAPLfunctionRunError.md) is called. This outputs a comment to the Write Window, which contains the name of the CAPL program, the type of error and an error index. With the help of the error index, the point in the CAPL source text which generated the error is found. Measurement is terminated after output of the comment.

The user can also call the function [runError](Functions/CAPLfunctionRunError.md) directly to generate assertions.
