[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateMostCriticalUnlock.md)

**CAPL Functions** » **Test Service Library** » **Checks** » **ChkCreate_MostCriticalUnlock, ChkStart_MostCriticalUnlock**

# ChkCreate_MostCriticalUnlock, ChkStart_MostCriticalUnlock

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

- `dword ChkCreate_MostCriticalUnlock();`
- `dword ChkStart_MostCriticalUnlock();`
- `dword ChkCreate_MostCriticalUnlock(Callback aCallback);`
- `dword ChkStart_MostCriticalUnlock(Callback aCallback);`

## Constructor

- `TestCheck::CreateMostCriticalUnlock();`
- `TestCheck::StartMostCriticalUnlock();`
- `TestCheck::CreateMostCriticalUnlock(Callback aCallback);`
- `TestCheck::StartMostCriticalUnlock(Callback aCallback);`

## Check Name

[MOST Light & Lock Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTLightLockObservation.md)

## Description

The check function monitors the occurrence of "CriticalUnlock" events.

A "CriticalUnlock" event is generated as soon an unlock occurs after a "Stable Lock" condition, which is longer than tUnlock (70 ms), or several unlocks occur successively, which together are longer than tUnlock (see MOST specification for more information).

This check always works on events. Therefore, it will not detect a current "CriticalUnlock" state, if this state has been entered before the check’s activation.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aCallback**: Name of the callback function, which should be called as soon as a "CriticalUnlock" event occurs. In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- CAPL callback does not exist.

## Example

—

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
