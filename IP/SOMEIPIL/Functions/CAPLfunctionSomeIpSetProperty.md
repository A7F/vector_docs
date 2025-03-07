# SomeIpSetProperty

[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpSetProperty.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpSetProperty**

## Tool Availability

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long SomeIpSetProperty(char propertyName[], int64 value); // form 1`
- `long SomeIpSetProperty(dword objHandle, char propertyName[], int64 value); // form 2`
- `long SomeIpSetProperty(dword objHandle, char propertyName[], char value); // form 3`
- `long SomeIpSetProperty(char propertyName[], byte buffer[]); // form 4`
- `long SomeIpSetProperty(char propertyName[], dword bufferLength, byte buffer[]); // form 5`
- `long SomeIpSetProperty(dword objHandle, char propertyName[], IP_Enpoint ip_endpoint); // form 6`

## Description

The behavior of the SOME/IP IL can be configured using properties. Properties can be set for the current bus context as well as on an object-specific basis for services, eventgroups, and events.

## Parameters

- **propertyName**: Name of the property to be set.
- **objHandle**: Handle of a service, eventgroup or event.
- **value**: New value of the property.
- **buffer**: A byte buffer containing the new value of the property.
- **bufferLength**: The size of or the number of bytes to copy from the parameter `buffer`.
- **ip_endpoint**: An ip endpoint where you can set ip address, port and transport protocol like UDP/TCP.

### Property Details

- **ClientId**: Default: Random. SomeIP-ClientId. Included in every message.
- **MaxUDPMessageLength**: Default: 1416. Sets the maximum allowed size of a SOME/IP message. Maximum size: 65519.
- **SDMulticastIp**: Default: 239.192.255.251. If SD is done per IPv4, SD sends multicasts to this IPv4 destination address.
- **SDMulticastPort**: Default: 30490. SD sends multicasts to this port and, if necessary, opens a local endpoint with this port.
- **SDMulticastIPv6**: Default: FF02::1. If SD is done per IPv6, SD sends multicasts to this IPv6 destination address.
- **VlanId**: This property may be set in `on preStart` to select a VLAN which needs to be configured for the current bus context.
- **UseSD**: Default: 1. May be set to zero before service instances and event groups are created which should not be registered to the service discovery.
- **SendMagicCookie**: Default: 1. Enable sending of magic cookie for TCP connections.
- **SDDefaultUnicastOptionIp**: Sets the default unicast IP address for the `SD IP Endpoint Option` within subscribe messages.
- **SDDefaultUnicastOptionPort**: Sets the default Port Number for the `SD IP Endpoint Option` within subscribe messages.
- **DisableTxCallbackForTP**: Default: 0. If set to 1, `OnSomeIpProcessTxMessage` callback will not be called for SOME/IP-TP messages too.
- **DetermineTCPRoleByConsumerProvider**: If true the TCP role is set by the consumer provider.
- **VlanPriority**: Sets the Vlan priority.
- **MaxSDMessageLength**: Sets an maximum length for the SOME/IP SD message.
- **SignalUpdateDelayInNs**: Sets a delay for updating signals.
- **MaxTCPRetries**: Sets a limit for TCP connection retries.

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

### Example form 1

```plaintext
SomeIpSetProperty("ClientId", 1);
```

### Example form 2

```plaintext
dword appEndpointHandle;
dword serviceHandle;

appEndpointHandle = SomeIpOpenLocalApplicationEndpoint(kUDP, 30501);
serviceHandle  = SomeIpCreateConsumedServiceInstance(appEndpointHandle, 1 /*serviceId*/, 1 /*instanceId*/);
SomeIpSetProperty(serviceHandle, "MajorVersion", 2);
```

### Example form 3

```plaintext
dword appEndpointHandle;
dword serviceHandle;

appEndpointHandle = SomeIpOpenLocalApplicationEndpoint(kUDP, 30501);
serviceHandle = SomeIpCreateConsumedServiceInstance(appEndpointHandle, 1 /*serviceId*/, 1 /*instanceId*/);
SomeIpSetProperty(serviceHandle, "SDConfigurationString","test123");
```

### Example form 4

```plaintext
Byte buffer[16] = {0xFF, 0x14, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x04, 0x00, 0x01};
SomeIpSetProperty("SDMulticastIpv6", buffer);
```

### Example form 5

```plaintext
Byte buffer[16] = {0xFF, 0x14, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x04, 0x00, 0x01};
SomeIpSetProperty("SDMulticastIpv6", 16, buffer);
```

### Example form 6

```plaintext
char serviceName[20] = "test_service";
dword csi;
IP_Endpoint ep;

ep = IP_Endpoint(UDP:[ff::1]:6000);
csi = SomeIpGetProvidedObjectHandle(serviceName);
SomeIpSDSetServiceStatus(csi, @this);
SomeIpSetProperty(csi, "SDEndpointOption", ep);
```

[See Also](javascript:void(0);)