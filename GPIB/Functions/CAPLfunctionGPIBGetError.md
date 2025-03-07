[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/Functions/CAPLfunctionGPIBGetError.md)

[CAPL Functions](../../CAPLfunctions.md) » [GPIB](../CAPLfunctionsGPIBOverview.md) » GPIBGetError

# GPIBGetError

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long GPIBGetError (void);
```

## Description

Returns the error variable. It is meaningful only when the **ERR** bit in the [status word](../CAPLfunctionsGPIBStatus.md) is set.

## Parameters

—

## Return Values

- [Error status](../CAPLfunctionsGPIBErrorCode.md)
- **28**: On error, if no GPIB driver is available

## Example

```plaintext
// "40" is not a valid GPIB address
GPIBDevChangePrimAddr(devDescr, 40);
if ( ( 1 << 15) & GPIBGetStatus() )
{
   write("ERR bit set in status word");
   if ( 4 == GPIBGetError() )
   {
      write("error is EARG: Invalid argument to function call");
   }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)