[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Objects/CAPLfunctionEthernetMacsecSecureEntity.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity

# EthernetMacsecSecureEntity

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

EthernetMacsecSecureEntity `<variable name>`;

## Method Syntax

- [EthernetMacsecSecureEntity::CreateRxSA](../Methods/CAPLfunctionCreateRxSA.md)
- [EthernetMacsecSecureEntity::CreateRxSC](../Methods/CAPLfunctionCreateRxSC.md)
- [EthernetMacsecSecureEntity::CreateTxSA](../Methods/CAPLfunctionCreateTxSA.md)
- [EthernetMacsecSecureEntity::CreateTxSC](../Methods/CAPLfunctionCreateTxSC.md)
- [EthernetMacsecSecureEntity::DeleteRxSA](../Methods/CAPLfunctionDeleteRxSA.md)
- [EthernetMacsecSecureEntity::DeleteRxSC](../Methods/CAPLfunctionDeleteRxSC.md)
- [EthernetMacsecSecureEntity::DeleteTxSA](../Methods/CAPLfunctionDeleteTxSA.md)
- [EthernetMacsecSecureEntity::DeleteTxSC](../Methods/CAPLfunctionDeleteTxSC.md)
- [EthernetMacsecSecureEntity::GetCapability](../Methods/CAPLfunctionGetCapability.md)
- [EthernetMacsecSecureEntity::GetConfidentialityOffset](../Methods/CAPLfunctionGetConfidentialityOffset.md)
- [EthernetMacsecSecureEntity::GetCurrentCipherSuite](../Methods/CAPLfunctionGetCurrentCipherSuite.md)
- [EthernetMacsecSecureEntity::GetDefaultRxSC](../Methods/CAPLfunctionGetDefaultRxSC.md)
- [EthernetMacsecSecureEntity::GetIncludeSCI](../Methods/CAPLfunctionGetIncludeSCI.md)
- [EthernetMacsecSecureEntity::GetReplayProtection](../Methods/CAPLfunctionGetReplayProtection.md)
- [EthernetMacsecSecureEntity::GetRxSAK](../Methods/CAPLfunctionGetRxSAK.md)
- [EthernetMacsecSecureEntity::GetRxSalt](../Methods/CAPLfunctionGetRxSalt.md)
- [EthernetMacsecSecureEntity::GetRxSCStats](../Methods/CAPLfunctionGetRxSCStats.md)
- [EthernetMacsecSecureEntity::GetSecYStats](../Methods/CAPLfunctionGetSecYStats.md)
- [EthernetMacsecSecureEntity::GetTxSAEnabled](../Methods/CAPLfunctionGetTxSAEnabled.md)
- [EthernetMacsecSecureEntity::GetTxSAK](../Methods/CAPLfunctionGetTxSAK.md)
- [EthernetMacsecSecureEntity::GetTxSalt](../Methods/CAPLfunctionGetTxSalt.md)
- [EthernetMacsecSecureEntity::GetTxSCStats](../Methods/CAPLfunctionGetTxSCStats.md)
- [EthernetMacsecSecureEntity::GetUseES](../Methods/CAPLfunctionGetUseES.md)
- [EthernetMacsecSecureEntity::GetValidateFrames](../Methods/CAPLfunctionGetValidateFrames.md)
- [EthernetMacsecSecureEntity::InitMacsec](../Methods/CAPLfunctionInitMacsec.md)
- [EthernetMacsecSecureEntity::InstallKey](../Methods/CAPLfunctionInstallKey.md)
- [EthernetMacsecSecureEntity::RegisterOnBeforeSendMKPDU](../Methods/CAPLfunctionRegisterOnBeforeSendMKPDU.md)
- [EthernetMacsecSecureEntity::RegisterOnBeforeSendMPDU](../Methods/CAPLfunctionRegisterOnBeforeSendMPDU.md)
- [EthernetMacsecSecureEntity::SetRxSAEnabled](../Methods/CAPLfunctionSetRxSAEnabled.md)
- [EthernetMacsecSecureEntity::SetTxSAEnabled](../Methods/CAPLfunctionSetTxSAEnabled.md)
- [EthernetMacsecSecureEntity::UpdateMkaICV](../Methods/CAPLfunctionUpdateMkaICV.md)
- [EthernetMacsecSecureEntity::UpdateSecY](../Methods/CAPLfunctionUpdateSecY.md)

## Description

Defines a variable of type **EthernetMacsecSecureEntity**. A correctly initialized EthernetMacsecSecureEntity provides direct access to the MACsec implementation of a measurement port, either the implementation provided in your CANoe DE product ('software implementation') or in the driver software, and, finally, in the MACsec capable PHY ('hardware implementation'). The methods provided by EthernetMacsecSecureEntity are the same as called by the MKA implemented in your CANoe DE product.

An EthernetMacsecSecureEntity must be initialized using the function [ethGetMacsecSecureEntity](../Functions/CAPLfunctionEthGetMacsecSecureEntity.md). Validity can be verified using the selector **isValid**.

## Parameters

- **name**: Variable name

## Selectors

- **isValid**: 1 if the secure entity has been correctly initialized, 0 otherwise. (Type: byte, Access: Read only)
- **hwPort**: The measurement port this secure entity is associated with. (Type: ethernetPort, Access: Read only)

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)