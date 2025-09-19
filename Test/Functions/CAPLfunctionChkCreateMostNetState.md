[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateMostNetState.md)

**CAPL Functions** » **Test Service Library** » **Checks** » **ChkCreate_MostNetState, ChkStart_MostNetState**

# ChkCreate_MostNetState, ChkStart_MostNetState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `dword ChkCreate_MostNetState(long aOldState, long aNewState);`
- `dword ChkStart_MostNetState(long aOldState, long aNewState);`
- `dword ChkCreate_MostNetState(long aOldState, long aNewState, Callback aCallback);`
- `dword ChkStart_MostNetState(long aOldState, long aNewState, Callback aCallback);`

## [Constructor](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::CreateMostNetState(long aOldState, long aNewState);`
- `TestCheck::StartMostNetState(long aOldState, long aNewState);`
- `TestCheck::CreateMostNetState(long aOldState, long aNewState, Callback aCallback);`
- `TestCheck::StartMostNetState(long aOldState, long aNewState, Callback aCallback);`

## Check Name

[MOST NetState Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTNetStateObservation.md)

## Description

This check is used to monitor the NetState state of the MOST network interface. Concrete checks can be implemented for any NetState state changes, and are triggered when a NetState event having the corresponding target state occurs with a specified initial state. The wildcard value –1 can be specified for one of the netstate parameters, if the check should monitor only the beginning or ending of a netstate. Both parameters can be set to wildcard value, if the check should detect any occurring netstate change. This check always works on events. Therefore, it will not detect a current netstate, that has been established before the time of the check’s activation, as a new netstate.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aCallback**: Name of the callback function that is to be called when a specified state change occurs. This parameter must be set for simulation nodes; it is optional for test modules.
- **aOldState**: Initial state of the state change to be monitored. Possible values are:
  - `0`: MostNetState_Undefined
  - `2`: MostNetState_PowerOff
  - `3`: MostNetState_NetInterfaceInit
  - `4`: MostNetState_ConfigNotOk
  - `5`: MostNetState_ConfigOk
  - `-1`: Wildcard value (any state is matched)
- **aNewState**: Target state of the state change to be monitored. Possible values the same as those for **aOldState**.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- CAPL callback does not exist.
- Invalid value specified for aOldState or aNewState.

## Example

—

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
