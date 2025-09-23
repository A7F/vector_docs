# ChkCreate_MostStableLock, ChkStart_MostStableLock

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

- `dword ChkCreate_MostStableLock(Callback aCallback);`
- `dword ChkStart_MostStableLock(Callback aCallback);`

## Constructor

[TestCheck::CreateMostStableLock(Callback aCallback)](../../../Shared/CAPL/General/ClassesAndObjects.md)
[TestCheck::StartMostStableLock(Callback aCallback)](../../../Shared/CAPL/General/ClassesAndObjects.md)

## Check Name

[MOST Light & Lock Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTLightLockObservation.md)

## Description

The check function monitors the occurrence of "StableLock" events.

A "StableLock" event is generated as soon as the hardware has been in the "Lock" condition for a period of time equal to or longer than tLock (see MOST Specification V 2.4), provided that no "Unlock" events have occurred.

This check always works on events. Therefore, it will not detect a current "StableLock" state, if this state has been entered before the check’s activation.

**Note**

Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aCallback**: Name of the callback function, which should be called as soon as a "StableLock" event occurs. In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- CAPL callback does not exist

## Example

—

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
