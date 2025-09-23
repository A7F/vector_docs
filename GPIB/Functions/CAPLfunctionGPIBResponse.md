# GPIBResponse

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
GPIBResponse (long deviceDescriptor, char queryString[], char resultString[]);
```

## Description

This function is called when the query returns. Users must implement this function and receive the original query string, the result as a string and the device ID.

## Parameters

- **deviceDescriptor**: The Device Descriptor of the device, that transmitted the response.
- **queryString**: The data transmitted in the [GPIBQuery](CAPLfunctionGPIBQuery.md) or [GPIBQueryEx](CAPLfunctionGPIBQueryEx.md) call, respectively.
- **resultString**: The device response.

## Return Values

—

## Example

```c
char myQuery[3] = "V?";
GPIBQuery(myDevice, "V?");
...
GPIBResponse (long deviceDescriptor, char queryString[], char resultString[])
{
   if (deviceDescriptor == myDevice)
   {
      if ( !strncmp(queryStr, myQuery, len))
      {
         @SysVarVoltage = GPIBGetFloatResult(resultString);
      }
   }
}
```

[strncmp](../../Other/Functions/CAPLfunctionStrnCmp.md)
