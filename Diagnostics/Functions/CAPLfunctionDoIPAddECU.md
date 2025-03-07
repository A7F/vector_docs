[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPAddECU.md)

**CAPL Functions** » **Diagnostics** » **DoIP_AddECU**

# DoIP_AddECU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

- [DoIP_AddEcu](#) and [DoIP_AddTester](CAPLfunctionDoIPAddTester.md) may cause on receiver side the rejection of DoIP messages with unknown logical addresses (in principle a kind of filtering).
- [DoIP_SetVehicleLogicalAddress](CAPLfunctionDoIPSetVehicleLogicalAddress.md) and [DoIP_SetTesterLogicalAddress](CAPLfunctionDoIPSetTesterLogicalAddress.md) determine the logical addresses used when sending.

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_AddECU( dword address);
```

## Description

Adds a valid DoIP ECU address to the DoIP layer.

## Parameters

- **address**: Logical DoIP address of an ECU. You must set at least one logical ECU address (e.g. the logical DoIP address of the DoIP entity).

## Example

```plaintext
DoIP_AddECU( 0x200);
DoIP_AddECU( 0x201);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)