[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSStopStimulation.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » StopStimulation

# StopStimulation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of appropriate channels of VT System modules.

## Method Syntax

`long SysVarNamespace.StopStimulation ();`

## Description

Stops the output of a stimulation signal. This resets the stimulation mode. Therefore it is not sufficient to call [StartStimulation](CAPLfunctionVTSStartStimulation.md) to start the output again. You also have to restore the stimulation mode, e.g. by calling [SetStimulationMode](CAPLfunctionVTSSetStimulationMode.md).

At the end of the execution of the command there is a short break before other commands will be executed. This means that the next functions will be executed after a short delay. With this procedure ensures that the stop command is executed effectively. The command should be called only in context of a test module setup but not in handler functions. In handler functions the correct execution of the stop command can not be ensured.

## Parameters

—

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT system. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

See example [SetStimulationMode](CAPLfunctionVTSSetStimulationMode.md)

[vtsStopStimulation](CAPLfunctionVTSvtsStopStimulation.md)
