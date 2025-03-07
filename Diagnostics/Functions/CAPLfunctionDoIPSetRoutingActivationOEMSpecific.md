[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPSetRoutingActivationOEMSpecific.md)

**CAPL Functions** » **Diagnostics** » **DoIP_SetRoutingActivationOEMSpecific**

# DoIP_SetRoutingActivationOEMSpecific

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetRoutingActivationOEMSpecific(long sendOEMSpecific, dword OEMspecific);
```

## Description

Sets the OEM-specific parameters in the Routing Activation Request Message.

## Parameters

- **sendOEMSpecific**
  - 0: Do not send the OEM specific field (default)
  - 1: Send the given value in the OEM specific field

- **OEMspecific**
  - Value to send if the OEM specific field is activated.

## Return Values

—

## Example

The message can also be configured from the DoIP.INI file

```plaintext
// Send a constant in the RAR message
DoIP_SetRoutingActivationOEMSpecific( 1, 0x31425927);
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)