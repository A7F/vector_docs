# diagIsValidValue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
long diagIsValidValue(diagResponse response, char[] parameterQualifier, long[] errorLevelOut);
```

## Description

Returns 1 if the parameter in the response object is valid, otherwise 0 is returned and the level of the problem (error or warning) is set in the output parameter field.

## Parameters

- **response**: The response object where the parameter is searched
- **parameterQualifier**: The qualifier of the parameter that is checked
- **errorLevelOut**: Return value if parameter could be checked:
  - `errorLevelOut[0]`:
    - `0`: Value is valid
    - `1`: Warning
    - `2`: Error

## Return Values

- **1**: Parameter value is valid, `errorLevelOut[0]` is set to 0.
- **0**: Parameter value is invalid, `errorLevelOut[0]` is set to the level of the problem.
- **`< 0`**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
on diagResponse Example_Service
{
    long errorLevelOut[1];
    long status;
    status = diagIsValidValue( this, "MyParameter", errorLevelOut);
    if( status == 1)
    {
        write( "Parameter value OK");
    } else if( status == 0)
    {
        if( errorLevelOut[0] == 1)
            write( "Warning.");
        else if( errorLevelOut[0] == 2)
            write( "ERROR!");
    } else
    {
        write( "Error %d checking parameter value!", status);
    }
}
```
