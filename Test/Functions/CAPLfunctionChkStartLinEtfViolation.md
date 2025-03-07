[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkStartLinEtfViolation.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkStart_LINETFViolation

# ChkStart_LINETFViolation

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword ChkStart_LINETFViolation (dword ETFFrameId, char[] CaplCallback);
dword ChkStart_LINETFViolation (dword ETFFrameId);
```

## Constructor

[TestCheck::StartLINETFViolation](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
TestCheck::StartLINETFViolation (dword ETFFrameId, char[] CaplCallback);
TestCheck::StartLINETFViolation (dword ETFFrameId);
```

## Description

Checks the format of a single response to ETF. An event will be generated if the first data byte does not match the protected ID of any of the associated frames (Slave failure).

Checks the collision resolution process. An event will be generated during collision resolution if one of the following is detected:

- No response for an associated frame (Slave failure)
- Wrong order of the associated frames. (Master failure)
- Associated frame is repeated (Master failure)
- Not all headers of associated frames are transmitted (Master failure)

**Note:** Dependent on the used parameter type, the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **ETFFrameId**: Frame identifier (8 bits) of an event triggered frame to verify
- **CaplCallback**: Name of CAPL callback function to be called on generated event. In simulation nodes, this parameter has to be set. In test modules, this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- Specified frame ID doesn’t match any of symbolic event-triggered frames
- Specified event-triggered frame contains no associated frames, i.e., nothing to verify
- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventReason](CAPLfunctionChkQueryEventReason.md)
- [ChkQuery_EventMessageContents](CAPLfunctionChkQueryEventMessageContents.md)
- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)
- [ChkQuery_EventMessageName](CAPLfunctionChkQueryEventMessageName.md)

## Example

```cpp
...
dword checkId;
// Create and start the check for LIN Event-triggered frame
// Parameters: Frame identifier of event-triggered frame to verify and optional CAPL 
// callback
checkId = ChkStart_LINETFViolation (0x3A, "CallbackLINETFViolation"); 
...
// CAPL callback for violation notification
void CallbackLINETFViolation (dword aCheckId)
{
    ChkQuery_EventStatusToWrite(aCheckId);
}
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)