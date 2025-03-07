[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetCurveType.md)

**CAPL Functions** » **VT System** » **vtsSetCurveType**

# vtsSetCurveType

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long vtsSetCurveType (char Namespace [], eVTSCurveType Type);
```

## Description

Specifies the form (the dynamic) of the stimulation signal.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **Type**: Values see [eVTSCurveType](../CAPLfunctionsVTSystemEnumeration.md#eVTSCurveType)

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified type is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

See example [vtsSetStimulationMode](CAPLfunctionVTSvtsSetStimulationMode.md)

[SetCurveType](CAPLfunctionVTSSetCurveType.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)