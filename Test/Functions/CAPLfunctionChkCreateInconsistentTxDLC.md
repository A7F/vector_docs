[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateInconsistentTxDLC.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_InconsistentTxDLC, ChkStart_InconsistentTxDLC

# ChkCreate_InconsistentTxDLC, ChkStart_InconsistentTxDLC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword ChkCreate_InconsistentTxDLC(Node aNode, char [] aCallback);
dword ChkStart_InconsistentTxDLC(Node aNode, char [] aCallback);
```

## Constructor

[TestCheck::CreateInconsistentTxDLC(Node aNode, char [] aCallback)](../../../Shared/CAPL/General/ClassesAndObjects.htm)
[TestCheck::StartInconsistentTxDLC(Node aNode, char [] aCallback)](../../../Shared/CAPL/General/ClassesAndObjects.htm)

## Check Name

[DLC](../../../TestCommands/CheckDescriptions/CDDLC.md)

## Description

Checks the DLC of all Tx messages of a node. The check condition is violated if the DLC of the message does not agree with the DLC specified in the database. Can only be started in the "on start" area of CAPL or during the measurement. However, the check may be set up as early as in the "pre start" area.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aNode**: Must exist in the database.
- **aCallback**: This parameter must be specified in simulation nodes; it is optional in test modules.

## Return Values

- **0**: Check could not be created and may not be referenced.
- **> 0**: Check was created successfully and can be referenced with the help of the returned (Handle) value.

## Possible Errors

- Specified node object does not exist in the database.
- CAPL Callback does not exist.

## Example

```cpp
// checks the DLC of all Tx messages of the node
checkId = ChkStart_InconsistentTxDlc(NodeToObserve);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
