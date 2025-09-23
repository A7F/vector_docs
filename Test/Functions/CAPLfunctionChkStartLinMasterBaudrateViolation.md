[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkStartLinMasterBaudrateViolation.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkStart_LINMasterBaudrateViolation

# ChkStart_LINMasterBaudrateViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkStart_LINMasterBaudrateViolation (float ClockTolerance);`
- `dword ChkStart_LINMasterBaudrateViolation (float ClockTolerance, char[] CaplCallback);`

## Constructor

- `TestCheck::StartLINMasterBaudrateViolation (float ClockTolerance);`
- `TestCheck::StartLINMasterBaudrateViolation (float ClockTolerance, char[] CaplCallback);`

## Description

Checks the LIN Master baudrate, by analyzing frame headers.

An event will be generated if the measured baudrate is outside of the specified range. The expected baudrate is taken from DB.

**Note:**

- For a LIN 2.0 compliance, the Master clock tolerance has to be in the range: [-0.5 .. 0.5] %.
- The actual baudrate is done in Synch Field with the sample rate of 1 second.
- This check works only when LIN hardware is not in Master mode, i.e., when an external Master is used.

Dependent on the used parameter type, the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **ClockTolerance**: Allowed Master clock tolerance. Measured baudrate expected to be in the range: B – B*aClockTolerance/100 \<= M \<= B + B* aClockTolerance/100; where M is measured baudrate and B is expected baudrate [specified in DB]. Unit: percents [%]
- **CaplCallback**: Name of CAPL callback function to be called on generated event. In simulation nodes, this parameter has to be set. In test modules, this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Check-specific Queries

- [ChkQuery_EventTiming](CAPLfunctionChkQueryEventTiming.md)

## Example

```plaintext
...
dword checkId;
// Create and start the check for LIN Master baudrate violation
checkId = ChkStart_LINMasterBaudrateViolation(0.5, "LINMasterBaudrateCallback");
...
// CAPL callback for violation notification
void LINMasterBaudrateCallback (dword aCheckId)
{
   ChkQuery_EventStatusToWrite(aCheckId);
}
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
