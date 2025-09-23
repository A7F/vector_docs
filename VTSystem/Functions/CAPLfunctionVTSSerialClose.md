[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSerialClose.md)

**CAPL Functions** » **VT System** » **SerialClose**

# SerialClose

**Valid for**: CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of channels that represent an external power supply in a power module **VT7001** respectively the system variable namespace that represents functionality common for the entire **VT7001** module.

## Method Syntax

```plaintext
long SysVarNamespace.SerialClose();
```

## Description

Closes the serial port of the VT System channel that is specified by the system variable namespace.

## Parameters

—

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.

## Example

See example [SerialConfigure](CAPLfunctionVTSSerialConfigure.md)

[vtsSerialClose](CAPLfunctionVTSvtsSerialClose.md)
