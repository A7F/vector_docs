[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSOnSerialError.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » OnSerialError

# OnSerialError

Valid for: CANoe DE • CANoe:lite DE

**Note**  
This callback function must be implemented in the CAPL program by the user to get notifications when an error has occurred in an operation on a serial port of the VT7001 module. The callback can be installed using the CAPL function [SerialSetOnErrorHandler](CAPLfunctionVTSSerialSetOnErrorHandler.md).

## Method Syntax

```plaintext
void <OnSerialError> (dword errorFlags);
```

## Description

The function is called when an error has occurred in an operation on a serial port of the VT7001 module.

## Parameters

- **errorFlags**: Cumulative summary of what went wrong. Bits are set to flag conditions.  
  Values see [eVTSCurrentMeasurementRange](../CAPLfunctionsVTSystemEnumeration.md#eVTSCurrentMeasurementRange)

  **Note**  
  Several error bits may be set at the same time. Some error flags are up to the driver manufacturer what they mean and when they are issued.

## Return Values

—

## Example

See example [SerialConfigure](CAPLfunctionVTSSerialConfigure.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
