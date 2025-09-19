[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/OCPP/CAPLfunctionCloseWebSocketConnection.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [OCPP](../CAPLFunctionsSmartChargingOverview.md#BMOCPP) » [General Functions](../CAPLFunctionsSmartChargingOverview.md#BMOCPPGeneralFunctions) » **CloseWebSocketConnection**

# CloseWebSocketConnection

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

`MethodReturnValueType CloseWebSocketConnection ( )`

## Description

This function is used to close the websocket and underlying TCP/TLS connection of the respective participant.

The CSMS closes its active connection but keeps listening for new connections. The **ChargingStation** closes its connection to the CSMS.

## Parameters

—

## Return Values

**MethodReturnValueType**

All function calls will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- `0`: OK
- `1`: InvalidArgument
- `2`: NoMatchingElementFound
- `3`: UnknownError

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
