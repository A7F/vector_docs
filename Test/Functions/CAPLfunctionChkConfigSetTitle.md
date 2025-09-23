[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkConfigSetTitle.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Configuration Functions](../CAPLfunctionsTSLConfigurationFunctions.md) » ChkConfig_SetTitle

# ChkConfig_SetTitle

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long ChkConfig_SetTitle (dword aCheckId, char aTitle[]);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
check.SetTitle(char aTitle[]);
```

## Description

Sets the title of a check. The check is displayed in the Write Window and the test report with this title.

## Parameters

- **aCheckId**: Identifier of the check
- **aTitle**: Title of the check

## Return Values

- **0**: Title is set successfully
- **-1**: Title could not be set due to invalid title parameter, e.g. empty title
- **-4**: Title could not be set due to invalid check identifier

## Example

```plaintext
// set title of the check
dword mCheckId;
mCheckId = ChkCreate_Timeout(1000);
ChkConfig_SetTitle(mCheckId, "Check Timeout");
ChkControl_Start(mCheckId);

TestCheck tc;
tc = TestCheck::CreateTimeout(1000);
tc.SetTitle("Check Timeout");
tc.Start();
```
