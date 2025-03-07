[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPSetVehicleLogicalAddress.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_SetVehicleLogicalAddress

# DoIP_SetVehicleLogicalAddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

- [DoIP_AddEcu](CAPLfunctionDoIPAddECU.md) and [DoIP_AddTester](CAPLfunctionDoIPAddTester.md) may cause on receiver side the rejection of DoIP messages with unknown logical addresses (in principle a kind of filtering).
- [DoIP_SetVehicleLogicalAddress](#) and [DoIP_SetTesterLogicalAddress](CAPLfunctionDoIPSetTesterLogicalAddress.md) determine the logical addresses used when sending.

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetVehicleLogicalAddress(dword logicalAddress);
```

## Description

Sets vehicle logical DoIP address sent in DoIP PDUs.

## Parameters

- **logicalAddress**: Address used (0x0000 to 0xFFFF)

## Return Values

—

## Example

The following example sets the Logical Address of a vehicle (used e.g. in Routing Activation Responses) and makes it known to the DoIP layer.

```plaintext
dword gGatewayLogAddress = 0x1000;
write("Logical address of vehicle = 0x%04x", gGatewayLogAddress);
DoIP_SetVehicleLogicalAddress( gGatewayLogAddress);
DoIP_AddECU( gGatewayLogAddress);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)