[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkStartLinSchedTableViolation.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkStart_LINSchedTableViolation

# ChkStart_LINSchedTableViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkStart_LINSchedTableViolation (dword TableIndex, duration Jitter);`
- `dword ChkStart_LINSchedTableViolation (dword TableIndex);`
- `dword ChkStart_LINSchedTableViolation (dword TableIndex, duration Jitter, char[] CaplCallback);`
- `dword ChkStart_LINSchedTableViolation (dword TableIndex, char[] CaplCallback);`

## Constructor

- `TestCheck::StartLINSchedTableViolation (dword TableIndex, duration Jitter);`
- `TestCheck::StartLINSchedTableViolation (dword TableIndex);`
- `TestCheck::StartLINSchedTableViolation (dword TableIndex, duration Jitter, char[] CaplCallback);`
- `TestCheck::StartLINSchedTableViolation (dword TableIndex, char[] CaplCallback);`

## Description

Checks a certain LIN schedule table for correspondence with the database definition. An event will be generated if:

- Slot frame is violated, i.e., transmitted frameID doesn’t match one defined in the corresponding time slot.
- Slot delay is not satisfied, i.e., the delay between two consecutive LIN headers is out of the range specified by the corresponding time slot and allowed Jitter.

**Note:**

- The check has to be started only when the specified schedule table is already running. This allows runtime synchronization, which may take a maximum of one schedule cycle time.
- This is not an appropriate function to check diagnostic schedule tables because silent slots can occur depending on the application.

**Note:**

- Depending on the used parameter type, the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous.
- Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **TableIndex**: Zero based index of schedule table to be checked.
- **Jitter**: Allowed deviation from the timing defined by schedule tables. For this value, usually Master’s Jitter is used. Measured slot delay should be in the range: D - Jitter \<= M \<= D + Jitter; where M is measured delay and D is expected delay. Unit: Can be set with ChkConfig_SetPrecision. Default: Master’s Jitter defined in LDF.
- **CaplCallback**: Name of CAPL callback function to be called on generated event. In simulation nodes, this parameter has to be set. In test modules, this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced.
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- Schedule table with specified index cannot be found.
- CAPL callback does not exist.

## Check-specific Queries

- [ChkQuery_EventFrameId](CAPLfunctionChkQueryEventFrameId.md)
- [ChkQuery_EventSchedSlotIndex](CAPLfunctionChkQueryEventSchedSlotIndex.md)
- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventReason](CAPLfunctionChkQueryEventReason.md)

## Example

```plaintext
...
dword checkId;
ChkConfig_SetPrecision(6); // switch to µs precision
// Create and start the check for LIN schedule table with index 0
checkId = ChkStart_LINSchedTableViolation(0, "LINSchedTableCallback"); 
ChkConfig_SetPrecision(3); // switch to ms precision (default)
...
// CAPL callback for violation notification
void LINSchedTableCallback (dword aCheckId)
{
   ChkQuery_EventStatusToWrite(aCheckId);
}
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
