[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkAddNode.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » Chk_AddNode

# Chk_AddNode

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Chk_AddNode (dword aCheckId, Node aNode, dword aAddress, dword aac, dword ig, dword sys, dword sysi, dword fct, dword fcti, dword ecui, dword mc, dword in);
```

## Constructor

[TestCheck::AddNode](../../../Shared/CAPL/General/ClassesAndObjects.md) (Node aNode, dword aAddress, dword aac, dword ig, dword sys, dword sysi, dword fct, dword fcti, dword ecui, dword mc, dword in);

## Check Name

—

## Description

Adds a J1939 node to an existing check.

## Parameters

- **aCheckId**: Check Id of an existing check.
- **aNode**: Name of the node to be checked. Must exist in database.
- **aAddress**: Address of the node. 0-253 or 0xFFFFFFFF if value of the node in database is used.
- **aac**: Arbitrary Address Capable 0..1 or 0xFFFFFFFF if value of the node in database is used.
- **ig**: Industry Group 0..7 or 0xFFFFFFFF if value of the node in database is used.
- **sys**: Vehicle System Instance 0..15 or 0xFFFFFFFF if value of database is used.
- **sysi**: Vehicle System 0..127 or 0xFFFFFFFF if value of the node in database is used.
- **fct**: Function 0..255 or 0xFFFFFFFF if value of the node in database is used.
- **fcti**: Function Instance 0..31 or 0xFFFFFFFF if value of the node in database is used.
- **ecui**: ECU Instance 0..7 or 0xFFFFFFFF if value of the node in database is used.
- **mc**: Manufacturer Code 0..2047 or 0xFFFFFFFF if value of the node in database is used.
- **in**: Identity Number 0..209715 or 0xFFFFFFFF if value of the node in database is used.

## Return Values

- **0**: Check could not be created and must not be referenced.
- **-1**: Node could not be added due to invalid parameter, e.g. invalid address.
- **-5**: Node could not be added due to invalid check identifier.

## Possible Errors

- Check Id does not exist.
- Node object does not exist in database.

## Example

```cpp
// checks the address claim violation of node N1
checkId = ChkCreate_J1939AddressClaimViolation ( N1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, 200, 0x01);

// add node N2 to the check
Chk_AddNode (checkId, N2, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1);
TestAddCondition(checkId);

// Start check
ChkControl_Start(checkId);

// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md) • [ChkCreate_J1939AddressClaimViolation](CAPLfunctionChkCreateJ1939AddressClaimViolation.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
