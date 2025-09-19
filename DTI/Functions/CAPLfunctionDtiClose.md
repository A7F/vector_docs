# DtiClose

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long DtiClose(dword pipeHandle);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
long DtiPipe::Close();
```

## Description

The function closes the specified pipe.

## Parameters

- **pipeHandle**: A handle to an open pipe.

## Return Values

- **0**: The pipe was closed successfully.
- **-1**: Failed to close the pipe.

## Example

```c
void closePipe(dword pipe)
{
    long result;

    if (pipe != 0)
    {
        result = DtiClose(pipe);
        if (result != 0)
            write("Failed to close the pipe!");
    }
}
```
