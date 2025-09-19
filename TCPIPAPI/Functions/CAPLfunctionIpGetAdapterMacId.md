[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpGetAdapterMacId.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetAdapterMacId

# IpGetAdapterMacId

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long IpGetAdapterMacId( dword ifIndex, byte macId[]);  // form 1`
- `qword IpGetAdapterMacId( dword ifIndex ); // form 2`

## Description

The function returns the MAC ID of the given interface.

## Parameters

- **ifIndex**: The 1-based network interface index. All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.

- **macId**: A byte array of 6 bytes size to return the MAC ID.

## Return Values

- **Form 1**
  - `0`: The function completed successfully.
  - `WSA_INVALID_PARAMETER (87)`: The specified network interface index was invalid.
  - `WSAEADDRNOTAVAIL (10049)`: No MAC ID found.

- **Form 2**
  - The MAC address as qword or 0, if failed

## Example

```plaintext
on start
{
  long result;
  long ifIndex;
  char adapterDesc[255];
  byte macId[6];

  ifIndex = 1;

  result = ipGetAdapterDescription(ifIndex, adapterDesc, elcount(adapterDesc));
  if( result != 0 )
  {
    writeLineEx(1, 3, "Failed to get the adapter description. Result: %d", result);
  }

  result = IpGetAdapterMacId(ifIndex, macId);
  if( result != 0 )
  {
    writeLineEx(1, 3, "Failed to get the adapter MAC ID. Result: %d", result);
  }
  else
  {
    writeLineEx(1, 0, "The Mac Id of Adapter %s is %02x:%02x:%02x:%02x:%02x:%02x",
    adapterDesc, macId[0], macId[1], macId[2], macId[3], macId[4], macId[5]);
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
