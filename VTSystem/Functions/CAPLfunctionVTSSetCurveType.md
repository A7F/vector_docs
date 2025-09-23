[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetCurveType.md)

**CAPL Functions** » **VT System** » SetCurveType

# SetCurveType

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of appropriate channels of VT System modules.

## Method Syntax

`long SysVarNamespace.SetCurveType (eVTSCurveType Type);`

## Description

Specifies the form (the dynamic) of the stimulation signal.

## Parameters

- **Type**: Values see [eVTSCurveType](../CAPLfunctionsVTSystemEnumeration.md#eVTSCurveType)

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified type is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT system. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

See example [SetStimulationMode](CAPLfunctionVTSSetStimulationMode.md)

[vtsSetCurveType](CAPLfunctionVTSvtsSetCurveType.md)
