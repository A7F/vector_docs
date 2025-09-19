# DoIP_SetTesterLogicalAddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

- [DoIP_AddEcu](CAPLfunctionDoIPAddECU.md) and [DoIP_AddTester](CAPLfunctionDoIPAddTester.md) may cause on receiver side the rejection of DoIP messages with unknown logical addresses (in principle a kind of filtering).
- [DoIP_SetVehicleLogicalAddress](CAPLfunctionDoIPSetVehicleLogicalAddress.md) and DoIP_SetTesterLogicalAddress determine the logical addresses used when sending.

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetTesterLogicalAddress(dword logicalAddress);
```

## Description

Sets logical DoIP address of the tester used for sending.

Note that ECU simulations will typically send responses to the tester address received in requests.

## Parameters

- **logicalAddress**: Address used (0x0000 to 0xFFFF)

## Return Values

—

## Example

```plaintext
DoIP_SetTesterLogicalAddress(0x1000);
```
