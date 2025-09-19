[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkStartSignalCycleTimeViolation.md)

**CAPL Functions** » **Test Service Library** » **Checks** » **ChkStart_SignalCycleTimeViolation**

# ChkStart_SignalCycleTimeViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword ChkStart_SignalCycleTimeViolation (Signal ObservedSignal, duration MinCycleTime, duration MaxCycleTime);
dword ChkStart_SignalCycleTimeViolation (Signal ObservedSignal, duration MinCycleTime, duration MaxCycleTime, char[] CaplCallback);
```

## Check Name

[Signal Cycle Time Absolute](../../../TestCommands/CheckDescriptions/CDSignalCycleTimeAbsolute.md)

## Description

Checks the occurrences of a signal. An event will be generated if the time between two consecutive signal occurrences is out of the specified range.

**Note**: Limit set to 0 is considered as "cycle time is undefined"; at least one limit has to be more than 0.

## Parameters

- **ObservedSignal**: Signal to observe. It must exist in DB
- **MinCyc**:
  - `0`: Minimum cycle time shall not be checked
  - `> 0`: Minimum allowed cycle time
  - Unit: Is set with [ChkConfig_SetPrecision()](CAPLfunctionChkConfigSetPrecision.md)
- **MaxCycleTime**:
  - `0`: Maximum cycle time shall not be checked
  - `> 0`: Maximum allowed cycle time
  - Unit: Is set with [ChkConfig_SetPrecision()](CAPLfunctionChkConfigSetPrecision.md)
- **CaplCallback**: Name of CAPL callback function to be called on generated event. In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- Signal does not exist in DB
- Range specified for cycle time is invalid
- Signal is not mapped to a message
- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventMessageName](CAPLfunctionChkQueryEventMessageName.md)
- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)
- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)

## Example

```plaintext
...
dword checkId;
// Create and start the check for LIN wake-up request
checkId = ChkStart_SignalCycleTimeViolation(Motor1State_Cycl::Motor1Temp,
          29,    // min. cycle time in ms
          32,    // max cycle time in ms
          "SigCycleTimeCallback");
...
// CAPL callback for violation notification
void SigCycleTimeCallback (dword aCheckId)
{
    ChkQuery_EventStatusToWrite(aCheckId);
}
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
