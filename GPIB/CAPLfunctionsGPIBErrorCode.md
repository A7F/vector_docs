[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/CAPLfunctionsGPIBErrorCode.md)

**CAPL Functions** » **GPIB** » Error Code

# GPIB Error Codes

*(Only available with GPIB & CANoe!)*

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE

## Error Code

Contains the error code of the current bus/device situation. It can be obtained using the function [GPIBGetError](Functions/CAPLfunctionGPIBGetError.md).  
Integer, Range: 0..28

## Explanation

- **0**: System error
- **1**: Function requires GPIB board to be CIC
- **2**: Write function detected no Listeners
- **3**: Interface board not addressed correctly
- **4**: Invalid argument to function call
- **5**: Function requires GPIB board to be System Controller
- **6**: I/O operation aborted
- **7**: Non-existent interface board
- **8**: Error performing DMA
- **10**: I/O operation started before previous operation completed
- **11**: No capability for intended operation
- **12**: File system operation error
- **14**: Command error during device call
- **15**: Serial poll status byte lost
- **16**: SRQ remains asserted
- **20**: The return buffer is full
- **21**: Address or board is locked
- **22**: The ibnotify Callback failed to rearm
- **23**: The input handle is invalid
- **26**: Wait already in progress on input ud
- **27**: The event notification was cancelled due to a reset of the interface
- **28**: CANoe spec.: no GPIB Bus available

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
