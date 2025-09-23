# RS232Close

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword RS232Close( dword port );
```

## Description

Closes a serial port.

The serial port will be closed for all nodes. One and the same port may be closed by several nodes (or repetitively). After closure other programs may use the serial port.

After closing the serial port the configuration of the port is lost. The next time the port is opened it will be configured with the system default.

## Parameters

- **port**: A number between 1 and 255 identifying a serial port.

## Return Values

- **0**: error
  - The error occurs if the serial port with the given number does not exist on the system.
- **1**: success

## Example

```plaintext
if ( 1==RS232Close(1) ) write("It works with port 1.");
```
