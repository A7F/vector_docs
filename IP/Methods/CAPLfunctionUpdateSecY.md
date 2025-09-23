[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionUpdateSecY.md)

## EthernetMacsecSecureEntity::UpdateSecY

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::UpdateSecY

### Method Syntax

[EthernetMacsecSecureEntity](../Objects/CAPLfunctionEthernetMacsecSecureEntity.md).UpdateSecY(EthernetMacsecSecYConfig secyConfig);

### Description

Configures the basic parameters of the secure entity.

### Parameters

- **secyConfig**: The settings to be updated are taken from the fields of the struct **EthernetMacsecSecYConfig**:
  - **currentCipherSuiteId**: The cipher suite to be used for MACsec.
  - **confidentialityOffset**: The confidentiality offset to be used (use CONFIDENTIALITY_NONE for authentication without encryption).
  - **protectFrames**: The protectFrames setting determines whether egress frames shall be encoded with MACsec.
  - **validateFrames**: The validateFrames setting determines whether ingress frames are required to be encoded with MACsec.
  - **replayProtect** and **replayWindow** specify replay protection.
  - **includeSCI** and **usES** settings determine the SC and ES bits of the MACsec tag control information (TCI).
  - The **controlledPortEnabled** flag determines whether the port is open, and must be set after the SecY is completely configured to enable MACsec traffic.

### Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

### Example

—
