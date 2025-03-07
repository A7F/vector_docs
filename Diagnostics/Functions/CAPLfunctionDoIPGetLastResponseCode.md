[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPGetLastResponseCode.md)

**CAPL Functions** » **Diagnostics** » **DoIP_GetLastResponseCode**

# DoIP_GetLastResponseCode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
long DoIP_GetLastResponseCode();
```

## Description

Returns the last negative response code received from the peer.

## Parameters

—

## Return Values

- **1**: No response code received yet, or this error does not have a specific response code
- **≥ 0**: Response code, depending on protocol and error type. Please refer to ISO13400 and HSFZ specifications for details.
- **Others**: reserved

## Example

```plaintext
void DoIP_ErrorInd( int error)
{
  write( "received error %d with error code %d", error, DoIP_GetLastResponseCode());
}
```

[DoIP_ErrorInd](CAPLfunctionDoIPErrorInd.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)