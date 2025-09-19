[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/CAPLfunctionsGPIBOverview.md)

[CAPL Functions](../CAPLfunctions.md) » GPIB CAPL Functions

# GPIB CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

**GPIB**

- Only available together with GPIB.
- GPIB is a bus protocol for networking measurement devices. Equivalent names are:
  - IEEE 488
  - HP-IB
  - IEC
- In order to be able to use GPIB functionality, a GPIB controller must be installed on the system.

## Functions

- [GPIBDevChangePrimAddr](Functions/CAPLfunctionGPIBDevChangePrimAddr.md): Changes the primary address of a device.
- [GPIBDevChangeSecAddr](Functions/CAPLfunctionGPIBChangeSecAddr.md): Changes the secondary address of a device.
- [GPIBDevClear](Functions/CAPLfunctionGPIBDevClear.md): Resets a device.
- [GPIBDevGotoLocal](Functions/CAPLfunctionGPIBDevGotoLocal.md): Sets a device into local mode.
- [GPIBDevOnline](Functions/CAPLfunctionGPIBDevOnline.md): Activates/deactivates the device.
- [GPIBDevOpen](Functions/CAPLfunctionGPIBDevOpen.md): Opens a GPIB device and returns a device ID.
- [GPIBGetCnt](Functions/CAPLfunctionGPIBGetCnt.md): Returns the number of bytes transferred by the last GPIB operation.
- [GPIBGetCtrlLineStatus](Functions/CAPLfunctionGPIBGetCtrlLineStatus.md): Returns the status of the GPIB control lines.
- [GPIBGetError](Functions/CAPLfunctionGPIBGetError.md): Returns the error variable.
- [GPIBGetFloatResult](Functions/CAPLfunctionGPIBGetFloatResult.md): Helps functions for extracting numeric values from GPIB response strings.
- [GPIBGetIntResult](Functions/CAPLfunctionGPIBGetIntResult.md): Helps functions for extracting numeric values from GPIB response strings.
- [GPIBGetStatus](Functions/CAPLfunctionGPIBGetStatus.md): Returns the status word.
- [GPIBOnError](Functions/CAPLfunctionGPIBOnError.md): Is called if a query or a write operation raised an error condition.
- [GPIBQuery](Functions/CAPLfunctionGPIBQuery.md): Query to the device.
- [GPIBQueryEx](Functions/CAPLfunctionGPIBQueryEx.md): Query to the device.
- [GPIBReqRelSysCtrl](Functions/CAPLfunctionGPIBReqRelSysCtrl.md): Sets or deletes the permission to send interface clear (IFC) or remote enabler (REN).
- [GPIBResponse](Functions/CAPLfunctionGPIBResponse.md): Is called when the query returns.
- [GPIBWriteNum](Functions/CAPLfunctionGPIBWriteNum.md): Writes GPIB command and numeric value to the device.
- [GPIBWriteStr](Functions/CAPLfunctionGPIBWriteStr.md): Writes GPIB command to the device.

**Note**

No explicit read functions are available. The response of GPIB devices is announced in the callback function [GPIBResponse](Functions/CAPLfunctionGPIBResponse.md). Here users can implement their specific code.

[Error Code](CAPLfunctionsGPIBErrorCode.md) • [Status](CAPLfunctionsGPIBStatus.md) • [GPIB: Overview](../../CANoeCANalyzer/Interfaces/GPIB.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
