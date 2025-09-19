[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetOutputSource.md)

**CAPL Functions** » **VT System** » **vtsSetOutputSource**

# vtsSetOutputSource

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long vtsSetOutputSource (char Target[], eVTSOutputSourceGroup Group, eVTSOutputSource Source);
```

## Description

Sets the source for the high voltage level for output. This settings can only be set for groups of channels.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **Group**: Values see [eVTSOutputSourceGroup](../CAPLfunctionsVTSystemEnumeration.md#eVTSOutputSourceGroup)
- **Source**: Values see [eVTSOutputSource](../CAPLfunctionsVTSystemEnumeration.md#eVTSOutputSource)

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified group or source is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

See example [vtsSetOutputMode](CAPLfunctionVTSvtsSetOutputMode.md)

[SetOutputSource](CAPLfunctionVTSSetOutputSource.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
