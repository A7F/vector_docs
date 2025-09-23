[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetCAK.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecConfiguration::SetCAK

# EthernetMacsecConfiguration::SetCAK

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

dword [EthernetMacsecConfiguration](../Objects/CAPLfunctionEthernetMacsecConfiguration.md).SetCAK(byte cak[], dword length);

## Description

Sets the connectivity association key (CAK) of the MACsec configuration from the given byte array.

## Parameters

- **cak[]**: A buffer from where to copy the CAK.
- **length**: The number of bytes to copy from the byte array. Note that a CAK must be either 16 or 32 bytes.

## Return Values

- **dword**: The number of bytes copied from the specified byte array.

## Example

—
