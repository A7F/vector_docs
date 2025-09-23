# AREthGetLastErrorText

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthGetLastErrorText( dword bufferLength, CHAR buffer[] );
```

## Description

Interface to retrieve the last error which occurs in the AUTOSAR Eth IL as string.

If the last called function has been successfully executed, the value 0 is returned. The call of the `AREthGetLastErrorText` function does **not** reset the saved error text.

## Parameters

- **bufferLength**: Number of characters
- **buffer**: Buffer receiving the error text

## Return Values

Number of copied characters.

## Example

```c
char buffer[1024];

// resume sending messages
AREthILControlResume();

// check if last function was executed correct
if((AREthGetLastErrorText(elcount(buffer),buffer)) != 0)
{
  write("AUTOSAR Eth IL error occurred: %s", buffer);
} // if
```

[See Also](javascript:void(0);)
