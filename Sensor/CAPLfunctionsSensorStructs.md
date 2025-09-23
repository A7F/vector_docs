[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/CAPLfunctionsSensorStructs.md)

[CAPL Functions](../CAPLfunctions.md) » [Sensor](CAPLfunctionsSensorOverview.md) » Structs

# Structs

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Sensor (PSI5): Psi5SensorFrameStruct

- **Member**: FrameType
  - **Type**: bitfield
  - **Short Description**: Bit 0 indicates, if the frame shall be empty. Bit 1 indicates, if this frame marks the end of a cycle.

- **Member**: StartDelayUs
  - **Type**: dword
  - **Short Description**: Start time of the frame (relative to sync pulse end or cycle start). Max value = 8191.

- **Member**: CrcMode
  - **Type**: [SensorPsi5CrcMode](CAPLfunctionsSensorEnumeration.md)
  - **Short Description**: Mode of CRC/parity calculation used for this frame

- **Member**: StartBits
  - **Type**: dword
  - **Short Description**: Content of the start bits

- **Member**: StartBitsCount
  - **Type**: dword
  - **Short Description**: Number of start bits

- **Member**: MessagingBits
  - **Type**: dword
  - **Short Description**: Content of the messaging bits

- **Member**: MessagingBitsCount
  - **Type**: dword
  - **Short Description**: Number of messaging bits

- **Member**: FrameControlBits
  - **Type**: dword
  - **Short Description**: Content of the frame control bits

- **Member**: FrameControlBitsCount
  - **Type**: dword
  - **Short Description**: Number of status bits

- **Member**: StatusBits
  - **Type**: dword
  - **Short Description**: Content of the status bits

- **Member**: StatusBitsCount
  - **Type**: dword
  - **Short Description**: Number of status bits

- **Member**: DataRegionBBits
  - **Type**: dword
  - **Short Description**: Content of the bits in data region B

- **Member**: DataRegionBBitsCount
  - **Type**: dword
  - **Short Description**: Number of bits in data region B

- **Member**: DataRegionABits
  - **Type**: dword
  - **Short Description**: Content of the bits in data region A

- **Member**: DataRegionABitsCount
  - **Type**: dword
  - **Short Description**: Number of bits in data region A

- **Member**: CrcBits
  - **Type**: dword
  - **Short Description**: Content of the CRC / parity bits

- **Member**: CrcBitsCount
  - **Type**: dword
  - **Short Description**: Number of CRC / parity bits

## Sensor (SENT): SentSensorFrameStruct

- **Member**: CrcMode
  - **Type**: [SensorSentCrcMode](CAPLfunctionsSensorEnumeration.md)
  - **Short Description**: Mode of CRC calculation used for this frame

- **Member**: StatusBits
  - **Type**: dword
  - **Short Description**: Content of the status region

- **Member**: DataBits
  - **Type**: dword
  - **Short Description**: Content of the data region

- **Member**: CrcBits
  - **Type**: dword
  - **Short Description**: Content of the CRC
