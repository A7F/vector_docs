[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TLSAPI/EventProcedures/CAPLfunctionOnObservedAndDecryptedTlsApplicationData.md)

[CAPL Functions](../../CAPLfunctions.md) » [TLS API](../CAPLfunctionsTLSOverview.md) » OnObservedAndDecryptedTlsApplicationData

# OnObservedAndDecryptedTlsApplicationData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnObservedAndDecryptedTlsApplicationData(IP_Endpoint sourceEndpoint, IP_Endpoint destinationEndpoint, byte data[], dword vlanIds[], dword applicationChannel)
```

```plaintext
void OnObservedAndDecryptedTlsApplicationData(IP_Endpoint sourceEndpoint, IP_Endpoint destinationEndpoint, byte data[], dword vlanIds[], dword applicationChannel, EthernetPort hardwareChannel)
```

## Description

If the CAPL program implements this callback, it is called when observed and decrypted TLS application data is available. The application channel allows to further select in the CAPL code, in which application data one is interested. In the case of an application-channel-based access OnObservedAndDecryptedTlsApplicationData with 5 parameters needs to be used. In contrast, with network-based access OnObservedAndDecryptedTlsApplicationData with 6 parameters, including the hardware channel, is required. The network access can be set in the CANoe options Bus Systems/Protocols, Ethernet. The data length can be retrieved with elcount(data) in the CAPL code.

## Parameters

- **sourceEndpoint**: Address and port to which the source socket is connected.
- **destinationEndpoint**: Address and port to which the destination socket is connected.
- **data**: Observed and decrypted TLS application data.
- **vlanIds**: vLAN Ids
- **applicationChannel**: ethernet application channel.
- **hardwareChannel**: ethernet hardware channel.

## Return Values

—

## Example

```plaintext
void OnObservedAndDecryptedTlsApplicationData(IP_Endpoint sourceEndpoint, IP_Endpoint destinationEndpoint, byte data[], dword vlanIds[], dword applicationChannel, EthernetPort hardwareChannel)
{
  char endpointStr[100];

  sourceEndpoint.PrintEndpointToString(endpointStr);
  if (sourceEndpoint.Address.IsIPv4Address() == 1)
  {
    write("Observed IPv4 package from src endpoint = %s on network %s with %d bytes of application data", endpointStr, hardwareChannel.networkname, elCount(data));
  }
  else if (sourceEndpoint.Address.IsIPv6Address() == 1)
  {
    write("Observed IPv6 package from src endpoint = %s on network %s with %d bytes of application data", endpointStr, hardwareChannel.networkname, elCount(data));
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)