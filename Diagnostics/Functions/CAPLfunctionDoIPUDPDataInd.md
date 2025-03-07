[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPUDPDataInd.md)

**CAPL Functions** » **Diagnostics** » _DoIP_UDPDataInd

# _DoIP_UDPDataInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```c
void _DoIP_UDPDataInd( char IPaddress[], BYTE data[]);
```

## Description

An UDP packet was received that cannot be interpreted by this DoIP implementation. The sender's IP address is given as the first argument, in text form.

**Note**  
Since the DoIP implementation is extended over time, the number of unknown packet types will be reduced. To process all UDP packets use the callback function [_DoIP_UDPInd](CAPLfunctionDoIPUDPInd.md). It is called for every UDP packet received before any processing is done.

## Parameters

- **IPaddress**: Address in text form, e.g. "169.254.32.1" (IPv4) or "2001::1" (IPv6).
- **data**: The raw data received, including complete header, if present.

## Return Values

—

## Example

```c
void _DoIP_UDPDataInd( char IPaddress[], BYTE data[])
{
  write( "_DoIP_UDPDataInd( '%s', [%d]<%02x ...>)", IPaddress
  , elcount( data), elcount(data) > 0 ? data[0] : 0);
}
```

[DoIP_UDPSend](CAPLfunctionDoIPUDPSend.md) • [_DoIP_UDPInd](CAPLfunctionDoIPUDPInd.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)