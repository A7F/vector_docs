[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionCreateRxSC.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **EthernetMacsecSecureEntity::CreateRxSC**

# EthernetMacsecSecureEntity::CreateRxSC

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

```plaintext
byte EthernetMacsecSecureEntity.CreateRxSC(EthernetMacsecSCI sci);
```

## Description

Creates a secure channel for receiving.

## Parameters

- **sci**: The secure channel id of the secure channel to be created.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.
  - Only one secure receive channel is supported. The call will fail if a transmit secure entity for this SecY already exists.

## Example

—
