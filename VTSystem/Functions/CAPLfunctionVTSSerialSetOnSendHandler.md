[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSerialSetOnSendHandler.md)

**CAPL Functions** » **VT System** » **SerialSetOnSendHandler**

# SerialSetOnSendHandler

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of channels that represent an external power supply in a power module **VT7001** respectively the system variable namespace that represents functionality common for the entire **VT7001** module.

## Method Syntax

`long SysVarNamespace.SerialSetOnSendHandler( char onSendCallback[]);`

## Description

Sets the callback that notifies when a send operation on the serial port of the specified channel is completed successfully.

The set callback must have following signature: `void <OnSerialSend>( byte sendBuffer[], dword number)`

## Parameters

- **onSendCallback**: CAPL callback function name.

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-3**: The passed callback does not have the required signature, i.e. number or type of the parameters are different than expected.

## Example

See example [SerialConfigure](CAPLfunctionVTSSerialConfigure.md)

[vtsSerialSetOnSendHandler](CAPLfunctionVTSvtsSerialSetOnSendHandler.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
