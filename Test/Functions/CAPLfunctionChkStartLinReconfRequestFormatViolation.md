[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkStartLinReconfRequestFormatViolation.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkStart_LINReconfRequestFormatViolation

# ChkStart_LINReconfRequestFormatViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkStart_LINReconfRequestFormatViolation ();`
- `dword ChkStart_LINReconfRequestFormatViolation (char[] CaplCallback);`

## Constructor

[TestCheck::StartLINReconfRequestFormatViolation](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::StartLINReconfRequestFormatViolation ();`
- `TestCheck::StartLINReconfRequestFormatViolation (char[] CaplCallback);`

## Description

Checks the format of LIN reconfiguration requests. An event will be generated if in a detected reconfiguration request at least one Slave attribute is violated.

**Note:**

- As reconfiguration request considered frames with ID=0x3C, carrying the Service Identifier byte (SID) in the range [0xB0..0xB7]
- Checked attributes: NAD, supplier ID, function ID, variant ID, message ID, protected ID, StartIndex.

Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **CaplCallback**: Name of CAPL callback function to be called on generated event. In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventReason](CAPLfunctionChkQueryEventReason.md)
- [ChkQuery_EventMessageContents](CAPLfunctionChkQueryEventMessageContents.md)

## Example

```plaintext
...
dword checkId;
// Create and start the check for LIN reconfiguration request format violation
checkId = ChkStart_LINReconfRequestFormatViolation("LINReconfRequestFormatCallback");
...
// CAPL callback for violation notification
void LINReconfRequestFormatCallback (dword aCheckId)
{
   ChkQuery_EventStatusToWrite(aCheckId);
}
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
