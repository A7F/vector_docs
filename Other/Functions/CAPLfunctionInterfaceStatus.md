[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionInterfaceStatus.md)

## InterfaceStatus

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » InterfaceStatus

### Function Syntax

```plaintext
void InterfaceStatus(long time, long channel, long status);
```

### Description

The callback can be inserted in the sections **callback function** or **function**.

The callback occurs when the status of the connection to the interface hardware is changed (e.g. when Windows reports a lost connection to a CAN/WLAN gateway or to a WLAN interface hardware for Car2x communication).

### Parameters

- **time**: Time, resolution 10us
- **channel**: The channel number
- **status**: Status of the channel  
  Values:  
  3015: The connection is lost

### Return Values

—

### Example

```c
void InterfaceStatus(long time, long channel, long status)
{
    if(status == 3015)
    {
        write("Time %f s, channel %d: The connection to the interface is lost!", ((float)time)/100000.0, channel);
    }
    else
    {
        //other status is not yet supported
    }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
