[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetAdapterGatewayAsString.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetAdapterGatewayAsString

# IpGetAdapterGatewayAsString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long IpGetAdapterGatewayAsString( dword ifIndex, char address[], dword count);
```

## Description

The function retrieves the string representation of the default gateway address associated with the specified network interface.

Gateway information is not yet available before the start of the measurement (on pre-start). Rather it is first available at the start of the measurement (on start) as soon as the stack has been completely initialized.

## Parameters

- **ifIndex**: The 1-based network interface index. All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.
- **address**: The buffer used to store the gateway IPv4 address string in dot notation.
- **count**: The size of the address buffer.

## Return Values

- **0**: The function completed successfully.
- **ERROR_NOT_ENOUGH_MEMORY (8)**: The address buffer was insufficient.
- **WSA_INVALID_PARAMETER (87)**: The specified network interface index was invalid.
- **WSAEADDRNOTAVAIL (10049)**: No gateway address available.

## Example

```plaintext
on start
{
  const dword IPV4_STR_SIZE = 16;   // IPv4 string size
  dword ifIdx;                     // interface index
  char ipv4GwAddrStr[IPV4_STR_SIZE]; // human readable IPv4 Gateway address.
  long result;                     // function result.

  for (ifIdx = 1; ifIdx <= IpGetAdapterCount(); ifIdx++)
  {
    result = IpGetAdapterGatewayAsString( ifIdx, ipv4GwAddrStr, elcount(ipv4GwAddrStr) );
    if (result == 0)
    {
      // success.
      write("IpGetAdapterGatewayAsString for adapter %d returned IPv4 gateway address: %s", ifIdx, ipv4GwAddrStr);
    }
    else
    {
      writeLineEx(1, 3, "IpGetAdapterGatewayAsString: Error %d", result);
    }
  }
}
```
