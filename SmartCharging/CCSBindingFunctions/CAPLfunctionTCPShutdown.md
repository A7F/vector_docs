[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionTCPShutdown.md)

# TCPShutdown

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » TCPShutdown

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```
MethodReturnValueType TCPShutdown ( )
```

## Description

The function can be used to trigger a closing of the TCP connection. If the remote side does not respond, the TCP connection is reset.

## Parameters

—

## Return Values

**MethodReturnValueType**

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- `0` OK
- `1` InvalidArgument
- `2` NoMatchingElementFound
- `3` UnknownError

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
