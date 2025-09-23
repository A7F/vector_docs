[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetRxSAK.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::GetRxSAK

# EthernetMacsecSecureEntity::GetRxSAK

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

`byte EthernetMacsecSecureEntity.GetRxSAK(EthernetMacsecSCI sci, byte AN, byte[] sak, dword& sakLength);`

## Description

Returns the current secure association key (SAK) of the receive SA specified by its SCI and AN.

## Parameters

- **sci**: The secure channel id of the secure channel of this SA to be queried.
- **AN**: The secure association number of the SA to be queried.
- **sak**: Byte buffer where the SAK will be returned.
- **sakLength**: Reference parameter where the actual SAK length will be returned. The value does not need to be initialized.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

The call will fail if:

- The secure channel referred to by the sci does not exist.
- The AN is not in range 0..3.
- The SA referred to by the association number does not exist.
- The buffer is too small. The **sakLength** will still be initialized to the expected buffer length.

## Example

—
