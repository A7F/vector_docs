[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSStartStimulation.md)

**CAPL Functions** » **VT System** » **StartStimulation**

# StartStimulation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of appropriate channels of **VT System** modules.

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax  
`long SysVarNamespace.StartStimulation ();`

## Description

Starts the output of a stimulation signal. A corresponding output mode must be set in advance.

## Parameters

—

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise, the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

See example [SetStimulationMode](CAPLfunctionVTSSetStimulationMode.md)

[vtsStartStimulation](CAPLfunctionVTSvtsStartStimulation.md)
