[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateUndefinedMessageReceived.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_UndefinedMessageReceived, ChkStart_UndefinedMessageReceived

# ChkCreate_UndefinedMessageReceived, ChkStart_UndefinedMessageReceived

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_UndefinedMessageReceived (char [] CaplCallback); // form 1`
- `dword ChkStart_UndefinedMessageReceived (char [] CaplCallback); // form 2`

## Constructor

[TestCheck::CreateUndefinedMessageReceived (char [] CaplCallback); // form 1](../../../Shared/CAPL/General/ClassesAndObjects.htm)
[TestCheck::StartUndefinedMessageReceived (char [] CaplCallback); // form 2](../../../Shared/CAPL/General/ClassesAndObjects.htm)

## Check Name

[Messages Known](../../../TestCommands/CheckDescriptions/CDMessagesKnown.md)

## Description

Observes the current bus and reports messages that are not defined.

If the CANoe configuration contains multiple buses, the current bus context has to be specified ([SetBusContext](../../Other/Functions/CAPLfunctionSetBusContext.md)) before the check configuration.

For FlexRay either only valid data frames or PDUs (according to the database type) are recognized as communication. Null Frames and Erroneous frames are ignored.

**Note on FlexRay PDU**

For a FlexRay PDU database this check also ignores all received frames!

- For a PDU database only PDUs are considered.
- For a FlexRay PDU database this test makes no sense, because only those PDUs, which are defined in the database, can be retrieved from frames.
- There cannot exist PDUs that are not defined in the database! Therefore, for a PDU database this check will always pass.

**Note**

Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous.

Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **CaplCallback**: In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Example

```plaintext
// observes the bus ‘CAN1’ for undefined messages
SetBusContext(getBusNameContext("CAN1"));
checkId = ChkStart_UndefinedMessageReceived();
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
checkId = ChkCreate_UndefinedMessageReceived("CallbackUnknownMsg");
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
