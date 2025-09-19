# DoIP_AddTester

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

- [DoIP_AddEcu](CAPLfunctionDoIPAddECU.md) and DoIP_AddTester may cause on receiver side the rejection of DoIP messages with unknown logical addresses (in principle a kind of filtering).
- [DoIP_SetVehicleLogicalAddress](CAPLfunctionDoIPSetVehicleLogicalAddress.md) and [DoIP_SetTesterLogicalAddress](CAPLfunctionDoIPSetTesterLogicalAddress.md) determine the logical addresses used when sending.

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_AddTester( dword address);
```

## Description

Adds a valid DoIP tester address to the DoIP layer.

## Parameters

- **address**: Logical DoIP address of a tester. You must set at least one valid logical tester address.

## Return Values

—

## Example

```plaintext
dword address;
address = DiagGetCommParameter("DoIP.TESTER_LogicalAddress");
DoIP_AddTester(address);
```
