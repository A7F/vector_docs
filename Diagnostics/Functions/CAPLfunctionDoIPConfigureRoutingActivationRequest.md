# DoIP_ConfigureRoutingActivationRequest

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```c
void DoIP_ConfigureRoutingActivationRequest(long mode, dword activationType, dword valueReserved);
```

## Description

Configures the Routing Activation Request Message sent by a tester.

## Parameters

- **mode**  
  0: Do not send a routing activation type  
  1: Send 1 byte activation type, value must be `<= 0xFF` (default)  
  2: Send 2 byte activation type, value must be `<= 0xFFFF`

- **activationType**  
  The value to send if an activation type is configured (i.e. mode is equal to 1 or 2).

- **valueReserved**  
  The value of the reserved field in the message.

## Return Values

—

## Example

You can also configure these values in the DoIP.INI file.

```plaintext
// Send the 2 byte activation type 0x1234, and set the reserved field
DoIP_ConfigureRoutingActivationRequest( 2, 0x1234, 0x76543210);
```
