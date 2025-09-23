# ChkCreate_MostShortUnlock, ChkStart_MostShortUnlock

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `dword ChkCreate_MostShortUnlock();`
- `dword ChkStart_MostShortUnlock();`
- `dword ChkCreate_MostShortUnlock(Callback aCallback);`
- `dword ChkStart_MostShortUnlock(Callback aCallback);`

## [Constructor](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::CreateMostShortUnlock();`
- `TestCheck::StartMostShortUnlock();`
- `TestCheck::CreateMostShortUnlock(Callback aCallback);`
- `TestCheck::StartMostShortUnlock(Callback aCallback);`

## Check Name

[MOST Light & Lock Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTLightLockObservation.md)

## Description

The check function monitors the occurrence of "ShortUnlock" events.

A "ShortUnlock" event occurs if there is no interpretable signal for a brief moment on the input of the connected MOST hardware (\< tUnlock, see also MOST specification) and the ring has been in a Light&Lock state before.

This check always works on events. Therefore, it will not detect a current "ShortUnlock" state, if this state has been entered before the check’s activation.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aCallback**: Name of the callback function, which should be called as soon as a "LightOff" event occurs. In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- CAPL callback does not exist

## Example

—

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
