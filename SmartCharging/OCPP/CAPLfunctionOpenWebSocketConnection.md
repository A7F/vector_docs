[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/OCPP/CAPLfunctionOpenWebSocketConnection.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [OCPP](../CAPLFunctionsSmartChargingOverview.md#BMOCPP) » [General Functions](../CAPLFunctionsSmartChargingOverview.md#BMOCPPGeneralFunctions) » OpenWebSocketConnection

# OpenWebSocketConnection

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

`MethodReturnValueType OpenWebSocketConnection ( )`

## Description

This function is used to open the websocket and underlying TCP/TLS connection of the respective participant.

The Charging Station tries to connect to the CSMS. The CSMS starts listening for new connections.

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

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
