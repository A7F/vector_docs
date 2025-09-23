# GetComputerName

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long GetComputerName(char buffer[], dword bufferSize);
```

## Description

Retrieves the fully qualified name of the computer.

## Parameters

- **buffer**: Space for the returned name.
- **bufferSize**: Length of the buffer.

## Return Values

0 if the function completed successfully, else unequal 0.

## Example

```plaintext
char buffer[50];
GetComputerName(buffer, elcount(buffer));
write("Computer name: %s", buffer);
```
