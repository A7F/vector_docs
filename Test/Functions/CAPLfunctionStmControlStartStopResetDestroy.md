[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionStmControlStartStopResetDestroy.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Stimulus Functions](../CAPLfunctionsTSLStimulusOverview.md) » StmControl_Start, StmControl_Stop, StmControl_Reset, StmControl_Destroy

# StmControl_Start, StmControl_Stop, StmControl_Reset, StmControl_Destroy

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long StmControl_Start(Stimulus::TstimulusId); // form 1`
- `long StmControl_Stop(Stimulus::TstimulusId); // form 2`
- `long StmControl_Reset(Stimulus::TstimulusId); // form 3`
- `long StmControl_Destroy(Stimulus::TstimulusId); // form 4`
- `long StmControl_Start(Stimulus::TstimulusId, dword duration); // form 5`

## [Destructor](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `stimulus.Destroy()`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- `stimulus.Start(); // form 1`
- `stimulus.Stop(); // form 2`
- `stimulus.Reset(); // form 3`
- `stimulus.Start(dword duration); // form 4`

## Description

The four control functions have the same Parameter. They only need an ID that refers to the specific stimulus.

## Parameters

- **Stimulus::TStimulusId**: The ID that is returned when a stimulus is created.
- **duration**: Runtime of stimulus

## Return Values

- **0**: Successful
- **-1**: Stimulus for given ID does not exist
- **-2**: Node layer module is deactivated and cannot process the request

## Example

—
