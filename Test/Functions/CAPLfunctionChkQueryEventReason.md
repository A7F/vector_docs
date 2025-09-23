# ChkQuery_EventReason

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ChkQuery_EventReason (dword checkId);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
check.QueryEventReason();
```

## Description

Retrieves the exact reason of firing event in the LIN specific check.

## Parameters

- **CheckId**: Identifier of the queried Check.

## Return Values

- **\< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **≥ 0**: Index of an event reason

## Available For

- [ChkStart_LINDiagDelayTimesViolation](CAPLfunctionChkStartLinDiagDelayTimesViolation.md)
  - Result: 1 - P2_min has been violated; 2- ST_min has been violated
- [ChkStart_LINReconfRequestFormatViolation](CAPLfunctionChkStartLinReconfRequestFormatViolation.md)
  - Result: Bit-mask is used. Indexing: least significant bit is 1.
  - Bit 1: Initial NAD is out of range
  - Bit 2: NAD references undefined Slave
  - Bit 3: Supplier ID does not match
  - Bit 4: Function ID does not match
  - Bit 5: Variant ID does not match
  - Bit 6: Message ID does not match
  - Bit 7: Protected ID does not match
  - Bit 8: ID Byte does not match (Conditional change NAD command)
  - Bit 9: BYTE Byte does not match (Conditional change NAD command)
- [ChkStart_LINSchedTableViolation](CAPLfunctionChkStartLinSchedTableViolation.md)
  - Result: 1 – Cannot synchronize during one cycle time; 2- Slot frame violated; 3- Slot delay violated; 4- Invalid empty slot
- [ChkStart_LINETFViolation](CAPLfunctionChkStartLinEtfViolation.md)
  - Result: 1 – Invalid format of single response (PID doesn’t match); 2 - No response during collision resolution; 3 - Wrong order of associated frames during collision resolution; 4 – Too many associated frames during collision resolution; 5 – Collision resolution is incomplete
- [ChkStart_LINWakeupRetryViolation](CAPLfunctionChkStartLinWakeupRetryViolation.md)
  - Result: 1 – Maximum number of retransmissions has been exceeded. 2..N: Timeout between retransmissions N-1..N has been exceeded

## Example

```c
testcase tcTSL_LINReconfRequest()
{
    dword checkId;
    long rqViolationReason;

    checkId = ChkStart_LINReconfRequestFormatViolation();
    testWaitForTimeout(5000);
    ChkControl_Stop(checkId);

    rqViolationReason = ChkQuery_EventReason(checkId);
    if (rqViolationReason & 0x1)
    {
        testStep("Evaluation", "Initial NAD is out of range");
    }
    if (rqViolationReason & 0x2)
    {
        testStep("Evaluation", "NAD references undefined Slave");
    }
    if (rqViolationReason & 0x4)
    {
        testStep("Evaluation", "Supplier ID does not match");
    }
    if (rqViolationReason & 0x8)
    {
        testStep("Evaluation", "Function ID does not match");
    }
    if (rqViolationReason & 0x10)
    {
        testStep("Evaluation", "Variant ID does not match");
    }
}
```
