# Checked Objects

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

The following object entries are checked during the object dictionary test with [coTfsODChkStdEntries](Functions/CAPLfunctionCoTfsOdChkStdEntries.md):

- **Index:** 0x1000
  - **Subindex:** 0x0
  - **Access Type:** readOnly
  - **Data Size:** uint32
  - **Default Value:** high word: don't care, low word: 0 or 400..499
  - **Mandatory Entry:** yes

- **Index:** 0x1003
  - **Subindex:** 0x0
  - **Access Type:** readWrite
  - **Data Size:** uint8
  - **Default Value:** 0
  - **Mandatory Entry:** no

- **Index:** 0x1005
  - **Subindex:** 0x0
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0x80 or 0x800000080
  - **Mandatory Entry:** no

- **Index:** 0x1006
  - **Subindex:** 0x0
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0
  - **Mandatory Entry:** no

- **Index:** 0x1007
  - **Subindex:** 0x0
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0
  - **Mandatory Entry:** no

- **Index:** 0x100C
  - **Subindex:** 0x0
  - **Access Type:** readOnly
  - **Data Size:** uint16
  - **Default Value:** 0
  - **Mandatory Entry:** no

- **Index:** 0x100D
  - **Subindex:** 0x0
  - **Access Type:** readWrite
  - **Data Size:** uint8
  - **Default Value:** 0
  - **Mandatory Entry:** no

- **Index:** 0x1012
  - **Subindex:** 0x0
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 100
  - **Mandatory Entry:** no

- **Index:** 0x1013
  - **Subindex:** 0x0
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0
  - **Mandatory Entry:** no

- **Index:** 0x1014
  - **Subindex:** 0x0
  - **Access Type:** readOnly
  - **Data Size:** uint32
  - **Default Value:** 0x80 + nodeId
  - **Mandatory Entry:** no

- **Index:** 0x1015
  - **Subindex:** 0x0
  - **Access Type:** readWrite
  - **Data Size:** uint16
  - **Default Value:** 0
  - **Mandatory Entry:** no

- **Index:** 0x1016
  - **Subindex:** 0x1
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0
  - **Mandatory Entry:** no

- **Index:** 0x1200
  - **Subindex:** 0x1
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0x600 + nodeId
  - **Mandatory Entry:** no

- **Index:** 0x1200
  - **Subindex:** 0x2
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0x580 + nodeId
  - **Mandatory Entry:** no

- **Index:** 0x1400
  - **Subindex:** 0x1
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0x200 + nodeId
  - **Mandatory Entry:** no

- **Index:** 0x1401
  - **Subindex:** 0x1
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0x300 + nodeId
  - **Mandatory Entry:** no

- **Index:** 0x1402
  - **Subindex:** 0x1
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0x400 + nodeId
  - **Mandatory Entry:** no

- **Index:** 0x1403
  - **Subindex:** 0x1
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0x500 + nodeId
  - **Mandatory Entry:** no

- **Index:** 0x1800
  - **Subindex:** 0x1
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0x180 + nodeId
  - **Mandatory Entry:** no

- **Index:** 0x1801
  - **Subindex:** 0x1
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0x280 + nodeId
  - **Mandatory Entry:** no

- **Index:** 0x1802
  - **Subindex:** 0x1
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0x380 + nodeId
  - **Mandatory Entry:** no

- **Index:** 0x1804
  - **Subindex:** 0x1
  - **Access Type:** readWrite
  - **Data Size:** uint32
  - **Default Value:** 0x480 + nodeId
  - **Mandatory Entry:** no

[CANopen Test Feature Set Node Layer](CAPLfunctionsCANopenNLTFSLevelOverview.md)
