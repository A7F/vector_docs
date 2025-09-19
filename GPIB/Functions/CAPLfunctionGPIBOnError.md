[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/Functions/CAPLfunctionGPIBOnError.md)

**CAPL Functions** » **GPIB** » **GPIBOnError**

# GPIBOnError

**Valid for**: CANoe DE

## Function Syntax

```
GPIBOnError (long deviceDescriptor, char query[], char response[], long status, long error);
```

## Description

This optional function is called if a query or a write operation ([GPIBWriteStr](CAPLfunctionGPIBWriteStr.md) or [GPIBWriteNum](CAPLfunctionGPIBWriteNum.md)) raised an error condition.

Users may implement this function and then receive the original query string or the data to be written, respectively. The result string, if any, is also returned, as well as the GPIB status word, the error code and the device descriptor.

## Parameters

- **deviceDescriptor**: The descriptor of the device that transmitted the response.
- **query**: The data transmitted in the failed `GPIBQuery…` or `GPIBWrite…` call, respectively.
- **response**: The data received from the device so far. The empty string if a write operation failure is reported.
- **status**: The GPIB status word.
- **error**: The GPIB error code.

## Return Values

—

## Example

The `GPIBOnError` callback function is used very much like [GPIBResponse](CAPLfunctionGPIBResponse.md). Refer to it for an example.

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
