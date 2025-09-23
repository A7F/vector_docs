[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSerialSetOnReceiveHandler.md)

**CAPL Functions** » **VT System** » **SerialSetOnReceiveHandler**

# SerialSetOnReceiveHandler

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of channels that represent an external power supply in a power module **VT7001** respectively the system variable namespace that represents functionality common for the entire **VT7001** module.

## Method Syntax

`long SysVarNamespace.SerialSetOnReceiveHandler( char onReceiveCallback[]);`

## Description

Sets the callback that notifies when data has been received on the serial port of the specified channel.

The set callback has to have following signature: `void <OnSerialReceive>( byte bffer[], dword number)`

## Parameters

- **onReceiveCallback**: CAPL callback function name.

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-3**: The passed callback does not have the required signature.

## Example

See example [SerialConfigure](CAPLfunctionVTSSerialConfigure.md)

[vtsSerialSetOnReceiveHandler](CAPLfunctionVTSvtsSerialSetOnReceiveHandler.md)
