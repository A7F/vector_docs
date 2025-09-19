[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TLSAPI/EventProcedures/CAPLfunctionOnObservedAndDecryptedTlsHandshakeData.md)

[CAPL Functions](../../CAPLfunctions.md) » [TLS API](../CAPLfunctionsTLSOverview.md) » OnObservedAndDecryptedTlsHandshakeData

# OnObservedAndDecryptedTlsHandshakeData

[Feature availability for your product](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void OnObservedAndDecryptedTlsHandshakeData(IP_Endpoint sourceEndpoint, IP_Endpoint destinationEndpoint, byte data[], dword vlanIds[], dword applicationChannel, RecordContentType contentType)
```

```plaintext
void OnObservedAndDecryptedTlsHandshakeData(IP_Endpoint sourceEndpoint, IP_Endpoint destinationEndpoint, byte data[], dword vlanIds[], dword applicationChannel, EthernetPort hardwareChannel, RecordContentType contentType)
```

## Description

If the CAPL program implements this callback, it is called when observed TLS handshake data is available. The application channel allows further selection in the CAPL code, in which handshake data one is interested. In the case of an application-channel-based access, `OnObservedAndDecryptedTlsHandshakeData` with 6 parameters needs to be used. In contrast, with network-based access, `OnObservedAndDecryptedTlsHandshakeData` with 7 parameters, including the hardware channel, is required. The network access can be set in the CANoe options Bus Systems/Protocols, Ethernet. The data length can be retrieved with `elcount(data)` in the CAPL code.

The record content type allows the user to select further for certain TLS handshake messages like TLS alerts.

## Parameters

- **sourceEndpoint**: Address and port to which the source socket is connected.
- **destinationEndpoint**: Address and port to which the destination socket is connected.
- **data**: Observed and decrypted TLS application data.
- **vlanIds**: vLAN Ids
- **applicationChannel**: Ethernet application channel.
- **hardwareChannel**: Ethernet hardware channel.
- **contentType**: Record Content Type. Enum containing `{eRecordContentHandshake, eRecordContentChangeCipherSpec, eRecordContentHeartbeat, eRecordContentAlert}` values.

## Return Values

—

## Example

```plaintext
void OnObservedAndDecryptedTlsHandshakeData(IP_Endpoint sourceEndpoint, IP_Endpoint destinationEndpoint, byte data[], dword vlanIds[], dword applicationChannel, EthernetPort hardwareChannel, enum RecordContentType contentType)
{
  char endpointStr[100];
  sourceEndpoint.PrintEndpointToString(endpointStr);

  if (sourceEndpoint.Address.IsIPv4Address() == 1)
  {
    write("Observed IPv4 package from src endpoint = %s on network %s with %d bytes of TLS handshake data with content type %s", endpointStr, hardwareChannel.networkname, elCount(data), contentType.Name());
  }
  else if (sourceEndpoint.Address.IsIPv6Address() == 1)
  {
    write("Observed IPv6 package from src endpoint = %s on network %s with %d bytes of TLS handshake data with content type %s", endpointStr, hardwareChannel.networkname, elCount(data), contentType.Name());
  }

  if (contentType == eRecordContentAlert)
  {
    write("TLS alert occurred");
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
