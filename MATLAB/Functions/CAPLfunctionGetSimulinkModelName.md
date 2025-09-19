[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MATLAB/Functions/CAPLfunctionGetSimulinkModelName.md)

**CAPL Functions** » [MATLAB Integration](../CAPLfunctionsMATLABOverview.md) » GetSimulinkModelName

# GetSimulinkModelName

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long GetSimulinkModelName( char[] buffer, dword bufferSize);
```

## Description

Gets the name of the Simulink model.

## Parameters

- **buffer**: The name of the Simulink model will be written to this buffer.
- **bufferSize**: The size of buffer in bytes.

## Return Values

On success 0, otherwise a value unequal to zero.

## Example

```plaintext
on start
{
  char buffer[30];
  if (GetSimulinkModelName(buffer, 30) == 0)
  {
    write("Simulink model: %s", buffer);
  }
}
```

[See Also](javascript:void(0);)
