[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/RS232/Functions/CAPLfunctionRS232Configure.md)

[CAPL Functions](../../CAPLfunctions.md) » [RS232](../CAPLfunctionsRS232Overview.md) » RS232Configure

# RS232Configure

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
dword RS232Configure( dword port, dword baudrate, dword numberOfDataBits, dword numberOfStopBits, dword parity ); // form 1
dword RS232Configure( dword port, dword baudrate, dword numberOfDataBits, dword numberOfStopBits, dword parity, dword enableParityCheck); // form 2
```

## Description

Configures a serial port.

Without setting up a configuration explicitly, the default configuration is used.

Default baudrate: 9600, 8 data bits, 1 stop bit, no parity.

If a [deprecated INI file](../CAPLfunctionsRS232DeprecatedIniFiles.md) exists, the data of the INI file will be used.

With form 2 of this function you can configure a serial port to use parity without letting the operating system verify parity correctness. This form should only be used if the communication to a device was not possible when using parity and form 1 of this function.

## Parameters

- **port**: A number between 1 and 255 identifying a serial port.
- **baudrate**: The symbol rate to use for reception and transmission. Typically, 9600 is used. There is a list of possible values which depends on the serial port. Normally, 115.200 is the allowed maximum.
- **numberOfDataBits**: The number of data bits within a transmission frame. 8 is used at most. Only values between 5 and 8 are possible. Not all values and not all combinations with other frame parameters may be supported by the serial port.
- **numberOfStopBits**: A code which sets the number of stop bits within a transmission frame.
  - **1**: 1 stop bit is used (1 has changed meaning compared to deprecated variant `RS232SetCommState`)
  - **2**: 2 stop bits are used

  **Note**: 1.5 stop bits are not supported any more.
  
- **parity**: A code which identifies the parity mode to use.
  - **0**: no parity used, i.e. frame contains no parity bit
  - **1**: odd parity
  - **2**: even parity

- **enableParityCheck**: Indicates whether to enable or disable the parity verification. This parameter is ignored if the parameter parity is set to 0 (no parity used).
  - **0**: parity verification disabled
  - **!=0 (≠0)**: parity verification enabled

## Return Values

- **0**: error
  - The error occurs if
    - the serial port with the given number does not exist on the system
    - the port has not been opened

- **1**: success

## Example

```plaintext
if ( 0!=RS232Configure(1,9600,8,1,0) )
   write("Set typical default at port 1.");
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
