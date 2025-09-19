# CAN Error Frame Selectors

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

You can access information of the error frame object using the following selectors:

### Identification
*Note: The validity of ID and DLC depends on the error type and the error position!*

- **CAN**: Transmission channel or channel through which the frame error has been received.  
  Value range: 1..32  
  Type: word

- **MsgChannel**: Transmission channel or channel through which the frame error has been received.  
  Value range: 1..32  
  Type: word

- **ID**: Message Identifier  
  This value is only available for some CAN hardware.  
  Type: dword

- **DLC**: Data Length Code  
  This value is only available for some CAN hardware.  
  Type: byte

### Message Times and Lengths

- **Time_ns**: Time stamp  
  Unit: nanoseconds  
  Type: Int64

- **Time**: Time stamp  
  Unit: 10µs  
  Type: dword

- **SOF**: Start-of-Frame time stamp in ns.  
  This value is only available for some CAN hardware.  
  Type: qword

- **ErrorPosition_Bit**: Bit index where an error has been detected by the controller.  
  This value is only available for some CAN hardware.  
  Type: dword

- **ErrorPosition_Time**: Difference between the time stamp of the error frame and the start of frame.  
  Unit: nanoseconds  
  This value is only available for some CAN hardware.  
  Type: dword

### Flags

- **FDF**: FD Format Indicator  
  This value is only available for some CAN hardware and a specific driver.  
  Type: byte

- **BRS**: CAN FD Bitrate Switch  
  This value is only available for some CAN hardware and a specific driver.  
  Type: byte

- **ESI**: CAN FD Error State Indicator  
  This value is only available for some CAN hardware and a specific driver.  
  Type: byte

- **Phase**: CAN FD phase.  
  This value is only available for some CAN hardware and a specific driver.  
  0: Error occurred in arbitration phase  
  1: Error occurred in data phase  
  Type: char

### Error Code

- **ErrorCode**: Error Code  
  Type: word

- **CtrlType**: CAN-controller type.  
  The error code format depends on the type of CAN controller.  
  0: unknown  
  1: SJA1000  
  2: CAN Core  
  Type: byte

### Data Access

- **Byte(x)**: Message data byte (unsigned 8 bit); possible values for x*: 0…63  
  Type: byte

- **Word(x)**: Message data word (unsigned 16 bit); possible values for x*: 0…62  
  The index is byte-oriented; for example, word(1) references to the data beginning at byte 1 and consists of byte 1…2 (16 bit).  
  Type: word

- **DWord(x)**: Message data word (unsigned 32 bit); possible values for x*: 0…60  
  The index is byte-oriented; for example, dword(1) references to the data beginning at byte 1 and consists of byte 1…4 (32 bit).  
  Type: dword

- **QWord(x)**: Message data word (unsigned 64 bit); possible values for x*: 0…56  
  Type: qword

- **char(x)**: Message data byte (signed 8 bit); possible values for x*: 0…63  
  Type: char

- **int(x)**: Message data word (signed 16 bit); possible values for x*: 0…62  
  The index is byte-oriented; for example, int(1) references to the data beginning at byte 1 and consists of byte 1…2 (16 bit).  
  Type: int

- **long(x)**: Message data word (signed 32 bit); possible values for x*: 0…60  
  The index is byte-oriented; for example, long(1) references to the data beginning at byte 1 and consists of byte 1…4 (32 bit).  
  Type: long

- **int64(x)**: Message data word (signed 64 bit); possible values for x*: 0…56  
  Type: int64

- **float(x)**: Message data interpreted as IEEE float (32 bit); possible values for x*: 0…60  
  Type: float

- **double(x)**: Message data interpreted as IEEE double (64 bit); possible values for x*: 0…56  
  Type: double
