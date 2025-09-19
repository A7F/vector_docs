[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkConfigSetCallback.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md) » ChkConfig_SetCallback

# ChkConfig_SetCallback

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long ChkConfig_SetCallback(dword aCheckId, char [] CaplCallback);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
check.SetCallback(char [] CaplCallback);
```

## Description

Sets a CAPL callback for the check. An already existing callback will be overwritten. This function can be used if the check itself has no syntax to create/start and to assign a callback.

## Parameters

- **aCheckId**: Must exist
- **CaplCallback**: The name of the CAPL callback function.

## Return Values

- **0**: successful
- **< 0**: error

## Example

```c
void callback(dword id)
{
  // do something
}
testcase TC1()
{
  int checkId;

  checkId = ChkCreate_MsgOccurrenceCount(MsgA1, 3);

  testAddCondition(checkId);
  ChkConfig_SetCallback(checkId, "callback");
  ChkControl_Start(checkId);

  testWaitForTimeout(3000);

  ChkControl_Stop(checkId);
  testRemoveCondition(checkId);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
