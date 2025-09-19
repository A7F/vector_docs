# DoIP_SetMulticastScopeId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetMulticastScopeId(dword scopeId);
```

## Description

Sets an IPv6 address scope ID for multicast requests, sent by a tester. The scope ID is equal to an adapter index of the tester node. See **ipGetAdapter** functions for more information.

The function allows to select an appropriate adapter for IPv6 multicast address, to be able, for example, to send multicast requests with a given VLAN tag.

**Note**  
`DoIP_SetMulticastScopeId` must be called before [DoIP_SetLocalIPaddress](CAPLfunctionDoIPSetLocalIPaddress.md) in order to use the scope ID with the specified local IP address.

## Parameters

- **scopeId**: Scope ID for selection of a network adapter for IPv6 multicast requests.

## Return Values

—

## Example

```plaintext
// returns TCP/IP adapter index for the given IP address
dword GetTCPIPAdapterScopeId(char ipAddr[])
{
  dword adapterCount;
  dword adapterIndex;

  dword addressCount;
  dword addressIndex;

  IP_Address ipAddresses[16];
  char ipAddressString[256];

  adapterCount = ipGetAdapterCount();
  for(adapterIndex = 1; adapterIndex <= adapterCount; adapterIndex++)
  {
    ipGetAdapterAddress(adapterIndex, ipAddresses, addressCount);
    for(addressIndex = 0; addressIndex < addressCount; addressIndex++)
    {
      ipAddresses[addressIndex].PrintAddressToString(ipAddressString);
      if(strncmp(ipAddr, ipAddressString, strlen(ipAddr)) == 0)
        return adapterIndex;
    }
  }

  return 0;
}

// identify the adapter scope ID for the tester IP address
// set it for sending multicast requests in corresponding network
dword scopeId;
scopeId = GetTCPIPAdapterScopeId(testerIPaddr);
DoIP_SetMulticastScopeId(scopeId);
```
