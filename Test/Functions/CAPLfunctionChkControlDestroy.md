[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkControlDestroy.md)

## ChkControl_Destroy

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md) » ChkControl_Destroy

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

```plaintext
long ChkControl_Destroy(dword aCheckId);
```

### Constructor

[Constructor](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
check.Destroy();
```

### Description

The check is destroyed and cannot be accessed anymore. Its resources are freed.

### Parameters

- **aCheckId**: Must exist

### Return Values

- **0**: successful
- **< 0**: error

### Possible Errors

- Check for given id does not exist

### Example

```plaintext
dword checkId;
dword numCheckEvents;

// start the Error Frame observation
checkId = ChkStart_ErrorFramesOccured();
// Add check as condition
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
// Remove check as condition
TestRemoveCondition(checkId);

// stop the check
ChkControl_Stop(checkId);

// destroy check
ChkControl_Destroy(checkId);
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
