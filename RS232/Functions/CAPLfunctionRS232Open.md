[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/RS232/Functions/CAPLfunctionRS232Open.md)

**CAPL Functions** » **RS232** » **RS232Open**

# RS232Open

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword RS232Open( dword port );
```

## Description

Opens a serial port.

**Note**: The serial port is available on exactly the node which executed the CAPL code. One and the same port may be opened by several nodes. If the port has been opened, other programs cannot access the serial port any more.

## Parameters

- **port**: A number between 1 and 255 identifying a serial port.

## Return Values

- **0**: error
  - The error occurs if:
    - the serial port with the given number does not exist on the system
    - another program uses the serial port according to the port number
- **1**: success

## Example

```plaintext
if ( 1==RS232Open(1) ) write("It works with port 1.");
```

[RS232 CAPL Functions: Deprecated INI File](../CAPLfunctionsRS232DeprecatedIniFiles.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
