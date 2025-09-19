# DoIP_SetProtocol

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetProtocol (dword protocolID);
```

## Description

Sets protocol version used in DoIP PDUs.

## Parameters

- **protocolID**  
  1: Draft version (2010)  
  2: First released ISO standard 2012 (ISO 13400-2 first edition 2012-06-01)  
  1000: HSFZ protocol  
  Others reserved

## Return Values

—

## Example

This value can also be configured globally on the diagnostics configuration dialog, **DoIP Main Settings**.

```plaintext
// Use early draft version of the protocol
DoIP_SetProtocol(1);
```
