[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkStartLinWakeupRetryViolation.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkStart_LINWakeupRetryViolation

# ChkStart_LINWakeupRetryViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkStart_LINWakeupRetryViolation (duration TimeoutAfterWakeup, duration TimeoutAfterThreeWakeups, float Tolerance, dword MaxRetryNum, char[] CaplCallback);`
- `dword ChkStart_LINWakeupRetryViolation (duration TimeoutAfterWakeup, duration TimeoutAfterThreeWakeups, float Tolerance, dword MaxRetryNum);`
- `dword ChkStart_LINWakeupRetryViolation (dword MaxRetryNum, char[] CaplCallback);`
- `dword ChkStart_LINWakeupRetryViolation (dword MaxRetryNum);`

## Constructor

[TestCheck::StartLINWakeupRetryViolation](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::StartLINWakeupRetryViolation (duration TimeoutAfterWakeup, duration TimeoutAfterThreeWakeups, float Tolerance, dword MaxRetryNum, char[] CaplCallback);`
- `TestCheck::StartLINWakeupRetryViolation (duration TimeoutAfterWakeup, duration TimeoutAfterThreeWakeups, float Tolerance, dword MaxRetryNum);`
- `TestCheck::StartLINWakeupRetryViolation (dword MaxRetryNum, char[] CaplCallback);`
- `TestCheck::StartLINWakeupRetryViolation (dword MaxRetryNum);`

## Description

Checks number of LIN wake-up signals and the time between them. An event will be generated if:

- Number of wake-up signals exceeds the specified maximum
- Timeout between two consecutive wake-up signals is out of the specified range.

**Note**: Dependent on the used parameter type, the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **TimeoutAfterWakeup**
  - `0`: Timeout between two consecutive retransmissions shall not be checked
  - `> 0`: Timeout between two consecutive retransmissions
  - Unit: Can be set with ChkConfig_SetPrecision.
  - Default: 150 ms.

- **TimeoutAfterThreeWakeups**
  - `0`: Timeout after each three retransmissions shall not be checked
  - `> 0`: Timeout after each three retransmissions
  - Unit: Can be set with ChkConfig_SetPrecision.
  - Default: 1.5 seconds

- **Tolerance**
  - Allowed tolerance for timeout values
  - Value range: [0 .. 100]
  - Unit: percents [%]
  - Default: 14%.

- **MaxRetryNum**
  - `0`: Maximum number of retransmissions shall not be checked
  - `> 0`: Maximum allowed number of retransmissions

- **CaplCallback**
  - Name of CAPL callback function to be called on generated event. In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- No parameters to validate
- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventReason](CAPLfunctionChkQueryEventReason.md)

## Example

```plaintext
...
dword checkId;
ChkConfig_SetPrecision(3); // set precision to ms
// Create and start the check for LIN Wake-Up signals
// Parameters to validate: Timeout between two wake-up signals – 150 ms,
// Timeout after each three wake-up signals – 1.5 sec, Allowed tolerance 2%, maximum 
// expected number of retransmitted Wake-Up signals - 4
checkId = ChkStart_LINWakeupRetryViolation (150, 1500, 2, 4, " LINWakeupRetryCallback"); 
...
// CAPL callback for violation notification
void LINWakeupRetryCallback (dword aCheckId)
{
    ChkQuery_EventStatusToWrite(aCheckId);
}
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
