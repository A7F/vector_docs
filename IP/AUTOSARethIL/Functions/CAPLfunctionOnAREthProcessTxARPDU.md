# OnAREthProcessTxARPDU

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long OnAREthProcessTxARPDU(dword sourceAddress, dword sourcePort, dword destinationAddress, dword destinationPort, dword length, char buffer[], dword headerID);` // form 1 is [deprecated](../../../Obsolete/CAPLfunctionsObsoleteOverview.md), use form 3
- `long OnAREthProcessTxARPDU(dword sourceAddress, dword sourcePort, dword destinationAddress, dword destinationPort, dword length, byte buffer[], dword headerID);` // form 2 is [deprecated](../../../Obsolete/CAPLfunctionsObsoleteOverview.md), use form 4
- `long OnAREthProcessTxARPDU(IP_Endpoint sourceEndpoint, IP_Endpoint destinationEndpoint, dword length, char buffer[], dword header_id);` // form 3
- `long OnAREthProcessTxARPDU(IP_Endpoint sourceEndpoint, IP_Endpoint destinationEndpoint, dword length, byte buffer[], dword header_id);` // form 4
- `long OnAREthProcessTxARPDU(IP_Endpoint sourceEndpoint, IP_Endpoint destinationEndpoint, dword length, char buffer[]);` // form 5
- `long OnAREthProcessTxARPDU(IP_Endpoint sourceEndpoint, IP_Endpoint destinationEndpoint, dword length, byte buffer[]);` // form 6

## Description

This callback is called before the interaction layer wants to send an AUTOSAR PDU. For PDUs with headers, form 3 or form 4 must be used, for headerless PDUs form 5 or form 6. This makes it possible to suppress the transmission.

## Parameters

- **sourceAddress**: IPv4 address of the local application endpoint.
- **sourcePort**: UDP or TCP port of the local application endpoint.
- **sourceEndpoint**: Endpoint of the local application endpoint.
- **destinationAddress**: IPv4 address of the target.
- **destinationPort**: UDP or TCP port of the target.
- **destinationEndpoint**: Endpoint of the target.
- **length**: Length of the data.
- **buffer**: Data to transmit.
- **headerId**: ID which is to be written in the header before the AUTOSAR PDU.

## Return Values

The AUTOSAR PDU is sent by the interaction layer, if the callback sends back **1**. Otherwise the transmission is suppressed.

## Example

```c
long OnAREthProcessTxARPDU(IP_Endpoint sourceEndpoint, IP_Endpoint destinationEndpoint, dword length, byte buffer[], dword header_id)
{ 
    // The AUTOSAR PDU is sent by the interaction layer, if the callback sends back 1
    IP_Endpoint UDP:192.168.1.10:4242 endpoint;

    if (sourceEndpoint.MatchesEndPoint(endpoint) == 1)
    {
        return 1; // send
    }
    else
    {
        return 0; // do not send
    }
}
```

[See Also](javascript:void(0);)
