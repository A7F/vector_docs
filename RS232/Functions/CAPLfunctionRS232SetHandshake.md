[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/RS232/Functions/CAPLfunctionRS232SetHandshake.md)

## RS232SetHandshake

[CAPL Functions](../../CAPLfunctions.md) » [RS232](../CAPLfunctionsRS232Overview.md) » RS232SetHandshake

### Function Syntax

```c
dword RS232SetHandshake( dword port, dword handshake, dword XonLimit, dword XoffLimit, dword XonChar, dword XoffChar );
dword RS232SetHandshake( dword port, dword handshake, dword XonLimit, dword XoffLimit, dword XonChar, dword XoffChar, dword timeout ); // deprecated
```

### Description

Sets handshake parameters on serial port.

**Note:** If you use hardware handshake, then the functions which change signal lines directly ([RS232SetSignalLine](CAPLfunctionRS232SetSignalLine.md), RS232EscapeCommFunc, RS232EscapeCommExt) may conflict with the automatic handshaking.

### Parameters

- **port**: A number between 1 and 255 identifying a serial port.
- **handshake**: Sets variant of handshake to use. Allowed values:
  - **0**: no handshake at all
  - **1**: hardware handshake, use DTR<->DSR
  - **2**: hardware handshake, use RTS<->CTS
  - **3**: hardware handshake, use RTS<->CTS, use "toggle" variant
  - **4**: software handshake, use Xon and Xoff characters

  DTR: Data-Terminal-Ready (from sender).  
  RTS: Request-To-Send (from sender).  
  DSR: Data-Set-Ready (from receiver).  
  CTS: Clear-To-Send (from receiver).

  **Note:** Mixtures of hardware and software handshake are not supported. For sake of compatibility, it is possible to set signal lines to fixed levels with this function. Please prefer for that purpose [RS232SetSignalLine](CAPLfunctionRS232SetSignalLine.md).

- **XonLimit**: Parameter for software flow control. Specifies the minimum number of bytes allowed in the input buffer before the XonChar is sent.
- **XoffLimit**: Parameter for software flow control. Specifies the maximum number of bytes in the input buffer before the XoffChar is sent. The maximum number of bytes allowed is calculated by subtracting this value from the size, in bytes, of the input buffer.

  **Note:** XonLimit and XoffLimit must be set properly to prevent errors, i.e. XonLimit < (input buffer size – XoffLimit) must apply.

- **XonChar**: Parameter for software flow control. It specifies the value of the XON character to start an operation (transmission as well as reception).
- **XoffChar**: Parameter for software flow control. It specifies the value of the XOFF character to suspend an operation (transmission as well as reception).

  **Note:** The transmitted data must not contain the XON and XOFF characters if software flow control is used. XON and XOFF are sent only once for each transition.

- **timeout**: Timeout in milliseconds for all send and receive operations.
  - **-1**: infinite
  - **`< 10`**: not allowed

  If this parameter isn't set, the **timeout** default value will be used: 5 seconds.

  **Note:** A timeout should not be used as it might stop a transmission that is not completed.

### Return Values

- **0**: error
  - The error occurs if:
    - the serial port with the given number does not exist on the system
    - the port has not been opened
- **1**: success

### Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)