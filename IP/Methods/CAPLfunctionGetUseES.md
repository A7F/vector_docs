[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetUseES.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **EthernetMacsecSecureEntity::GetUseES**

# EthernetMacsecSecureEntity::GetUseES

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Method Syntax

`byte EthernetMacsecSecureEntity.GetUseES(byte& useES);`

## Description

Returns preset for the end station (ES) flag in the tag control information (TCI). When this bit is set, the recipient will assume the SCI can be formed from the frame’s source address and port number 1.

When this bit is clear, and SC bit is also clear, the receiving secure channel cannot be determined from the frame’s contents. The secure entity will fall back to the default receive secure channel (see [GetDefaultRxSC](CAPLfunctionGetDefaultRxSC.md)) for decoding the frame.

Note that ES=1 and SC=1 is an invalid TCI setting.

## Parameters

- **useES**: The reference parameter where the queried value will be returned.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
