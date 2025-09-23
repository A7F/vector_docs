[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/RS232/CAPLfunctionsRS232DeprecatedIniFiles.md)

# RS232 CAPL Functions: Deprecated INI File

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

INI files called `v24.INI` or `rs232.INI` can be used to configure ports. Though, it is not advised to do so. It is much clearer to set parameters directly by use of [RS232Configure](Functions/CAPLfunctionRS232Configure.md). The configuration files have to be inserted into the CANoe DE product `Exec32` directory.

## Sections and Descriptions

- **[COMsettings]**: General section the key-value pairs of which apply to all ports used.
  - **Note**: Values of specific sections overwrite the values of the general section for a specific port.

- **[COMsettings_COM1]**: Specific section the key-value pairs of which apply to one port specified (COM1).

- **[COMsettings_COM255]**: Specific section the key-value pairs of which apply to one port specified (COM255).

- **[Queue-Sizes]**: General section to give (serial port) driver queue sizes which will be used as recommendation by the driver. Applies to all ports.
  - **Note**: Values of specific sections overwrite the values of the general section for a specific port.

- **[Queue-Sizes_COM1]**: Specific section to give (serial port) driver queue sizes which will be used as recommendation by the driver. Applies to one port (COM1).

- **[Queue-Sizes_COM255]**: Specific section to give (serial port) driver queue sizes which will be used as recommendation by the driver. Applies to one port (COM255).

## Key and Values

- **Section: [COMsettings]**
  - **Key: COMport**: List of identifiers for serial ports which will be opened at first call which opens a port ([RS232Open](Functions/CAPLfunctionRS232Open.md) and RS232SetCommState). The list is separated by semicolons (e.g. COMport=1;2;3).

- **Section: [COMsettings_COMx] with x a number between 1 and 255**
  - **Key: UseCOMspecificSettings**: Either 0 or 1. If 1, then the section is enabled. If 0, then the values of the specific section are not used.

- **Section: [COMsettings] as well as [COMsettings_COMx] with x a number between 1 and 255**
  - **Key: Baud**: The symbol rate to use for reception and transmission.
    - **Note**: Typically, 9600 is used. There is a list of possible values which depends on the serial port. Normally, 115.200 is the allowed maximum.

  - **Key: ByteSize**: The number of data bits within a transmission frame.
    - **Note**: 8 is used at most. Only values between 5 and 8 are possible. Not all values and not all combinations with other frame parameters may be supported by the serial port.

  - **Key: StopBits**: A code which sets the number of stop bits within a transmission frame.
    - 0: 1 stop bit is used; it is the typical and most reasonable value
    - 1: 1.5 stop bits are used
    - 2: 2 stop bits are used

  - **Key: Parity**: A code which identifies the parity mode to use.
    - 0: no parity used, i.e. frame contains no parity bit
    - 1: odd parity
    - 2: even parity

- **Section: [Queue-Sizes] as well as [Queue-Sizes _COMx] with x a number between 1 and 255**
  - **Key: QueueSize_Rx**: The size of the receiver buffer of the driver. The size is given in bytes. The range of numbers and the constraints (e.g. dividable by 8) are dependent on the driver. The number will be used as recommendation by the driver.
    - **Note**: If you specify a small number which is really used by the driver, then frequent buffer overruns may happen and the connection may not be stable.

  - **Key: QueueSize_Tx**: The size of the transmission buffer of the driver. The size is given in bytes. The range of numbers and the constraints (e.g. dividable by 8) are dependent on the driver. The number will be used as recommendation by the driver.
    - **Note**: If you specify a small number which is really used by the driver, then frequent buffer overruns may happen and the connection may not be stable.

## Example

```plaintext
; THIS FILE IS DEPRECATED
; it is better to program the serial interface by means of CAPL
; standard section, settings used for ALL ports
; can be overwritten by a prot specific section
; settings can be controlled directly by CAPL functions

[COMsettings]
; "COMport" opens "shared" ports the results of which will be given
; to all listening nodes (nodes implementing a callback)
; e.g. "COMport=2;3 ;5" means to open COM2, COM3 and COM5 as shared port
; note: the former limitation that only ports listed for "COMport" could be used
;     within CAPL has been removed
COMport=1

; "Baud" sets baudrate
; note that only specific settings are possible
; the exact settings depend on the serial driver
; typical maximum is 115200
Baud=9600

; "ByteSize" means "number of data bits" within one transmission frame
; typically 5..8 are allowed
; 8 is most reasonable for best performance
ByteSize=8

; "StopBits" means "number of stop bits" within one transmission frame
; possible values:
; 0 : 1    StopBits (!!!)
; 1 : 1.5 StopBits
; 2 : 2    StopBits
; example: "StopBits=0" means to use one stop bit
; 0 is most reasonable for best performance
StopBits=0

; "Parity" determines parity bit in frame
; possible values:
; 0: No parity
; 1: Even parity
; 2: Odd parity
; 0 is most reasonable for best performance
Parity=0

; specific section for COM1 port
; (can only be used if port is available)
; uses the same key-value-pairs as general section
; i.e. "Baud", "ByteSize", "StopBits", "Parity"
[COMsettings_COM1]
; "UseCOMspecificSettings" needs to be set to really enable usage of
; specific section
; possible values: 0 or 1
UseCOMspecificSettings=1
; following values overwrite the values out of the general section for COM1
; if and only if "UseCOMspecificSettings=1" holds true
Baud=115200
ByteSize=8
StopBits=0
Parity=0
```
