[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateAllNodesDead.md)

**CAPL Functions** » **Test Service Library** » **Checks** » ChkCreate_AllNodesDead, ChkStart_AllNodesDead

# ChkCreate_AllNodesDead, ChkStart_AllNodesDead

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_AllNodesDead (Duration aMaxQuietTime, char [] CaplCallback);`
- `dword ChkStart_AllNodesDead (Duration aMaxQuietTime, char [] CaplCallback);`

## Constructor

- `TestCheck::CreateAllNodesDead (Duration aMaxQuietTime, char [] CaplCallback);`
- `TestCheck::StartAllNodesDead (Duration aMaxQuietTime, char [] CaplCallback);`

## Check Name

[Node Active (Check Description)](../../../TestCommands/CheckDescriptions/CDNodeActive.md)

## Description

All monitored nodes must send at least one of their Tx messages within a specified interval. Otherwise an event will be triggered. Each node is checked separately, so a dead node is recognized even if others are alive. Gateway nodes require that the bus context corresponds to the network that is being observed. For FlexRay only valid data frames and PDUs are recognized as communication, Null Frames and Erroneous frames are ignored.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMaxQuietTime**: Upper limit of time interval. > 0; default unit [ms], if not changed with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).
- **CaplCallback**: In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Check-specific Queries

- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)

## Example

```plaintext
// checks that at least one message is sent in each 100 ms
checkId = ChkStart_AllNodesDead (100);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
