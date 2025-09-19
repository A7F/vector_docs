[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Sensor/CAPLfunctionsSensorEnumeration.md)

[CAPL Functions](../CAPLfunctions.md) » [Sensor](CAPLfunctionsSensorOverview.md) » Enumeration

# Enumeration

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Sensor: SensorErrorCode

- **Value**: 0  
  **Enum**: eSensorNoError  
  **Short Description**: The function call succeeded

- **Value**: 1  
  **Enum**: eSensorFunctionNotSupported  
  **Short Description**: The function is not supported on the given callee

- **Value**: 2  
  **Enum**: eSensorInvalidArgument  
  **Short Description**: One or more arguments had an invalid value

- **Value**: 3  
  **Enum**: eSensorInvalidState  
  **Short Description**: The callee is in a state that does not support the function call

- **Value**: 4  
  **Enum**: eSensorDisturbanceNotSupported  
  **Short Description**: The given disturbance is not supported on the callee

- **Value**: 5  
  **Enum**: eSensorTargetNotFound  
  **Short Description**: No callee with the given name was found

- **Value**: 6  
  **Enum**: eSensorOperationFailed  
  **Short Description**: An internal error occurred while processing the call

- **Value**: 7  
  **Enum**: eSensorSendBufferFull  
  **Short Description**: Operation failed because no free send buffer is available

## Sensor (PSI5): SensorPsi5CrcMode

- **Value**: 0  
  **Enum**: ePsi5AutoCrc  
  **Short Description**: CRC/parity field content is calculated and set automatically

- **Value**: 1  
  **Enum**: ePsi5ManualCrc  
  **Short Description**: CRC/parity field content is set as given in struct

- **Value**: 2  
  **Enum**: ePsi5WrongCrc  
  **Short Description**: CRC/parity field is set to a value that is explicitly wrong

## Sensor (SENT): SensorSentCrcMode

- **Value**: 0  
  **Enum**: eSentAutoCrc  
  **Short Description**: CRC/parity field content is calculated and set automatically

- **Value**: 1  
  **Enum**: eSentManualCrc  
  **Short Description**: CRC/parity field content is set as given in struct

- **Value**: 2  
  **Enum**: eSentWrongCrc  
  **Short Description**: CRC/parity field is set to a value that is explicitly wrong

- **Value**: 3  
  **Enum**: eSentRecommendedCrc  
  **Short Description**: Explicitly uses the new, recommended CRC algorithm to calculate the CRC field content

- **Value**: 4  
  **Enum**: eSentLegacyCrc  
  **Short Description**: Explicitly uses the legacy CRC algorithm to calculate the CRC field content

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
