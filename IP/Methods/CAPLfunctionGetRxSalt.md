[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetRxSalt.md)

# EthernetMacsecSecureEntity::GetRxSalt

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::GetRxSalt

Valid for: CANoe DE

## Method Syntax

`byte EthernetMacsecSecureEntity.GetRxSalt(EthernetMacsecSCI sci, byte AN, byte[] salt, dword& saltLength);`

## Description

Returns the current XPN salt value of the receive SA specified by its SCI and AN.

## Parameters

- **sci**: The secure channel id of the secure channel of this SA to be queried.
- **AN**: The secure association number of the SA to be queried.
- **salt**: Byte buffer where the salt value will be returned.
- **saltLength**: Reference parameter where the actual salt length will be returned. The value does not need to be initialized.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

The call will fail if:

- The secure channel referred to by the sci does not exist.
- The AN is not in range 0..3.
- The SA referred to by the association number does not exist.
- The buffer is too small. The **saltLength** will still be initialized to the expected buffer length.

## Example

—
