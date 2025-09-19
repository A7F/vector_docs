[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetToTCP.md)

## IP_Endpoint::SetToTCP

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » IP_Endpoint::SetToTCP

### Method Syntax

`long IP_Endpoint::SetToTCP();`

### Description

Sets the transport protocol to TCP.

### Parameters

—

### Return Values

- **0**: Success

### Example

```plaintext
on start
{
  IP_Endpoint 192.168.1.1:4000 addr;
  addr.SetToTCP();
  if (addr.IsTCP())
  {
    write("Is TCP endpoint");
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
