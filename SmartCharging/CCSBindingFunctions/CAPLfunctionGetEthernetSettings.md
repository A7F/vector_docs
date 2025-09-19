[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionGetEthernetSettings.md)

**CAPL Functions** » **Smart Charging** » **CCS (Communication Setup)** » **Shared Functions** » **GetEthernetSettings**

# GetEthernetSettings

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

`MethodReturnValueType GetEthernetSettings(out uint64 MACAddress_out, out string IPv6Address_out)`

## Description

Gets the configured MAC address as uint64 and the IPv6 address as string in colon notation. For further transformation of IPv6 address see i.e. [IpGetAddressAsArray](../../TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsArray.md).

## Parameters

- **MACAddress_out**: Gets the MAC address.
- **IPv6Address_out**: Gets the IPv6 address in colon notation.

## Return Values

**MethodReturnValueType**

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- `0`: OK
- `1`: InvalidArgument
- `2`: NoMatchingElementFound
- `3`: UnknownError

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
