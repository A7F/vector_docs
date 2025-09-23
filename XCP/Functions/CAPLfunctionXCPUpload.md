[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionXCPUpload.md)

[CAPL Functions](../../CAPLfunctions.md) » [XCP](../CAPLfunctionsXCPOverview.md) » xcpUpload

# xcpUpload

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long xcpUpload(char namespace[], char variable[]); // form 1`
- `long xcpUpload(sysvar sysvar); // form 2`

## Callback

- `void OnXcpUpload (char namespace[], char variable[], long errorIndication);`

## Description

Initiates an upload of the XCP parameter from ECU and updates the dedicated system variable.

After finishing of the upload the callback function `OnXcpUpload` is called to indicate the upload status.

Use the return value of `xcpUpload` to check if an error occurred during initiation of the upload.

Use the **errorIndication** parameter of the `OnXcpUpload` callback function to check for errors occurred during the upload, if an error during call of `xcpUpload` occurs `OnXcpUpload` is not called.

## Parameters

- **namespace**: Namespace of the corresponding system variable.
- **variable**: Name of the corresponding system variable.
- **sysvar**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysvar::".
- **errorIndication**:
  - 0: OK
  - -4: Device is not connected

## Return Values

- **0**: OK
- **-1**: System variable of the parameter was not found
- **-2**: Operation not allowed

## Example

```c
testcase TC_SignalInactive ()
{
    xcpUpload("XCP::ECU","testword0");
    ....
}

// Callback function:
void OnXcpUpload (char namespace[], char variable[], long returnValue)
{
    if (returnValue==0)
        write("Systemvariable updated: %s %s", namespace,variable);
}
```
