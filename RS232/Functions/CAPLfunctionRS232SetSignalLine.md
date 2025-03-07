[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/RS232/Functions/CAPLfunctionRS232SetSignalLine.md)

**CAPL Functions** » **RS232** » **RS232SetSignalLine**

# RS232SetSignalLine

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword RS232SetSignalLine( dword port, dword line, dword state );
```

## Description

Sets signal lines on serial port.

**Note**: If you use hardware handshake, then this function may conflict with the automatic handshaking.

## Parameters

- **port**: A number between 1 and 255 identifying a serial port.
- **line**: Specifies signal line of which the state shall be set.
  - **0**: RTS
  - **1**: DTR
  - Data-Terminal-Ready (from sender).
  - RTS: Request-To-Send (from sender).
- **state**:
  - **0**: disabled
  - **1**: enabled

## Return Values

- **0**: error
  - The error occurs if:
    - the serial port with the given number does not exist on the system
    - the port has not been opened
- **1**: success

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)