[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateJ193976FunctionalSafetyCheck.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_J1939_76_FunctionalSafetyCheck

# ChkCreate_J1939_76_FunctionalSafetyCheck

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_J1939_76_FunctionalSafetyCheck(Node producerNode, char[] callback1);`
- `dword ChkCreate_J1939_76_FunctionalSafetyCheck(unsigned long producerAddress, char[] callback1);`
- `dword ChkStart_J1939_76_FunctionalSafetyCheck(Node producerNode, char[] callback1);`
- `dword ChkStart_J1939_76_FunctionalSafetyCheck(unsigned long producerAddress, char[] callback1);`

## Constructor

[Constructor](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::Create_J1939_76_FunctionalSafetyCheck(Node producerNode, char[] callback2);`
- `TestCheck::Create_J1939_76_FunctionalSafetyCheck(unsigned long producerAddress, char[] callback2);`

## Description

Observes the J1939-76 functional safety communication according to [J1939-76](../../../CANoeCANalyzer/J1939/j1939basics/j1939FunctionalSafety.md). It is possible to observe all nodes or only a specific node.

During the check, the following verifications are made:

- Consecutive sequence numbers of the SHM.
- Validation of the CRC of the SHM on receipt of the associated SDM.
- Missing or too late SDM after a SHM.
- Missing SHM before an SDM.
- Compliance with SRVTMaximum (calculation as described above).

A SHM is always recognized by the unique PGN 3584 (0E00h). After a SHM has been received, the check recognizes the associated SDM by means of the CAN ID (without priority) contained in the payload of the SHM and can then perform the validation.

The database attribute [FsJ1939NeedsSHM](../../../CANoeCANalyzer/J1939/j1939basics/j1939CanDbAttributes.md) is used to check for a missing SHM. For each PG where the attribute has the value **True**, a SHM must have preceded.

## Parameters

- **producerNode**: Producer node from database.
- **producerAddress**: Address of the producer ECU.
  - Possible values:
    - 0 – 253: Observe the J1939-76 communication of the ECU with this address
    - 254, -1 (or 0xFFFFFFFF): Observe the J1939-76 communication of all ECUs
- **callback1**: This parameter is optional.
  - Name of the callback which is called when the check fails.
  - Signature: `void Callback( dword checkId )`
- **callback2**: This parameter is optional.
  - Name of the callback which is called when the check fails.
  - Signature: `void Callback( TestCheck check )`

## Return Values

- **0**: Check could not be created and must not be referenced.
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Example

```plaintext
dword checkId;
checkId = ChkStart_J1939_76_FunctionalSafetyCheck(N1);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functional Safety (J1939-76)](../../../CANoeCANalyzer/J1939/j1939basics/j1939FunctionalSafety.md) • [Test Service Library: Configuration Functions](../CAPLfunctionsTSLConfigurationFunctions.md) • [Test Service Library: Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
