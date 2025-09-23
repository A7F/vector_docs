[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetOutputSource.md)

**CAPL Functions** » **VT System** » **SetOutputSource**

# SetOutputSource

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note:** The function can only be called on system variable namespaces of appropriate channels of **VT System** modules.

## Method Syntax

`long SysVarNamespace.SetOutputSource (eVTSOutputSourceGroup Group, eVTSOutputSource Source);`

## Description

Sets the source for the high voltage level for output. This setting can only be set for groups of channels.

## Parameters

- **Group**: Values see [eVTSOutputSourceGroup](../CAPLfunctionsVTSystemEnumeration.md#eVTSOutputSourceGroup)
- **Source**: Values see [eVTSOutputSource](../CAPLfunctionsVTSystemEnumeration.md#eVTSOutputSource)

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-3**: The specified group or source is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

See example [SetOutputMode](CAPLfunctionVTSSetOutputMode.md)

[vtsSetOutputSource](CAPLfunctionVTSvtsSetOutputSource.md)
