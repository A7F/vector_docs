[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionCreateTxSC.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **EthernetMacsecSecureEntity::CreateTxSC**

# EthernetMacsecSecureEntity::CreateTxSC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

`byte EthernetMacsecSecureEntity.CreateTxSC(EthernetMacsecSCI sci);`

## Description

Creates a secure channel for transmitting.

## Parameters

- **sci**: The secure channel id of the secure channel to be created.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.
  - Only one secure transmit channel is supported. The call will fail if a transmit secure entity for this SecY already exists.

## Example

—