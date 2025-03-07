[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenEmergency.md)

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenEmergency

# CANopenEmergency

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword CANopenEmergency(dword nodeId, dword active, dword errorCode, byte[] specificData, dword dataSize);
```

## Description

Activates/deactivates an emergency error code.

## Parameters

- **nodeId**: CANopen node ID.
- **active**:
  - 0: Emergency code deactivated
  - 1: Emergency code activated
- **errorCode**: Error code number.
- **specificData**: Additional data transmitted with the emergency message.
- **dataSize**: Size of **specificData**.

## Return Values

- **1**: Invalid nodeID
- **2**: Invalid parameter
- **3**: Invalid errorCode
- **4**: Invalid dataSize
- **5**: No CANopen license
- **6**: No CAN channel
- **7**: No client with nodeID
- **8**: No EMCY handler defined in the object directory (check DCF file)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)