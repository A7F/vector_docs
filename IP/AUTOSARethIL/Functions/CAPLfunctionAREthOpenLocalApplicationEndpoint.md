[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthOpenLocalApplicationEndpoint.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthOpenLocalApplicationEndpoint**

# AREthOpenLocalApplicationEndpoint

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword AREthOpenLocalApplicationEndpoint(dword transportProtocol, dword port); // form 1`
- `dword AREthOpenLocalApplicationEndpoint(dword transportProtocol, dword port, dword ipv4Address); // form 2`
- `dword AREthOpenLocalApplicationEndpoint(dword transportProtocol, dword port, byte ipv6Address[]); // form 3`
- `dword AREthOpenLocalApplicationEndpoint(IP_Endpoint localIPEndpoint); // form 4`

## Description

Opens an application endpoint. An endpoint represents a socket. The IP address is the IP address of the current interface, which is determined by the bus context.

Services can be assigned to an Application Endpoint using the [AREthCreateProvidedServiceInstance](CAPLfunctionAREthCreateProvidedServiceInstance.md) or [AREthCreateConsumedServiceInstance](CAPLfunctionAREthCreateConsumedServiceInstance.md) function. An Application Endpoint can be closed again using the [AREthCloseLocalApplicationEndpoint](CAPLfunctionAREthCloseLocalApplicationEndpoint.md) function.

**Note**

This only works with the node TCP/IP stack; in the Windows TCP/IP stack the interface cannot be determined by the bus context. The [SD](javascript:void(0)) endpoints can be configured using the properties of AUTOSAR Eth IL (see also: [AREthSetProperty](CAPLfunctionAREthSetProperty.md)).

## Parameters

- **transportProtocol**
  - 6: TCP
  - 17: UDP

- **port**
  - UDP: Port on which the messages can be both sent and received.
  - TCP: Port on which the messages can be either sent or received. If a node is to receive and send messages, two Application Endpoints must be set up: one for the receive direction and the other for the send direction.

- **ipv4Address**
  - Bind the socket to this IPv4 address. The address should be given in [network byte order](../../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).

- **ipv6Address**
  - Bind the socket to this IPv6 address. The 16 bytes in the array should be given in [network byte order](../../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).

- **localIPEndpoint**
  - Object of type **IP_Endpoint** that contains the address/port of the local endpoint.

## Return Values

- **0**
  - An error occurred. The error can be evaluated using the [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function.

- **>0**
  - Handle of the created Application Endpoint.

## Example

```c
void Initialize()
{
  DWORD aep; // Application Endpoint handle
  DWORD psi; // provided service handle
  DWORD peg; // provided Eventgroup handle
  DWORD pev; // provided Event handle

  // open Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(IP_Endpoint(UDP:192.168.0.1:50002));

  // create Service Instance
  psi = AREthCreateProvidedServiceInstance(aep,10,1);
  // create Eventgroup
  peg = AREthAddProvidedEventGroup(psi,1);

  // create Event and add Event to Eventgroup
  pev = AREthAddEvent(psi, 1, "OnPrepareEvent1");
  AREthAddEventToEventgroup(peg, pev);

  // ensure that Event is sent cyclically
  AREthSetProperty(pev,"CycleTimeMs",1000);
}

void OnPrepareEvent1(DWORD eventHandle, DWORD messageHandle)
{
  // this function is called before the Event is sent. Parameters
  // can be specified here.
}
```

[See Also](javascript:void(0);)