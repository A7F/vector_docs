[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthSetProperty.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthSetProperty**

# AREthSetProperty

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long AREthSetProperty(char propertyName[], int64 value); // form 1`
- `long AREthSetProperty(dword objHandle, char propertyName[], int64 value); // form 2`
- `long AREthSetProperty(dword objHandle, char propertyName[], char value); // form 3`
- `long AREthSetProperty(char propertyName[], byte buffer[]); // form 4`
- `long AREthSetProperty(char propertyName[], dword bufferLength, byte buffer[]); // form 5`
- `long AREthSetProperty(dword objHandle, char propertyName[], IP_Enpoint ip_endpoint); // form 6`

## Description

The behavior of the AUTOSAR Eth IL can be configured using properties. Properties can be set for the current bus context as well as on an object-specific basis for services, Eventgroups, and Events.

## Parameters

- **propertyName**: Name of the property to be set.
  - **ClientId**: Default Value: Random, Form: 1, Description: SomeIP-ClientId. Included in every message
  - **MaxUDPMessageLength**: Default Value: 1416, Form: 1, Description: Sets the maximum allowed size of a SOME/IP message. Maximum size: 65519
  - **SDMulticastIp**: Default Value: 239.192.255.251, Form: 1, Description: If SD is done per IPv4, SD sends multicasts to this IPv4 destination address
  - **SDMulticastPort**: Default Value: 30490, Form: 1, Description: SD sends multicasts to this port and, if necessary, opens a local endpoint with this port
  - **SDMulticastIPv6**: Default Value: FF02::1, Form: 4, 5, Description: If SD is done per IPv6, SD sends multicasts to this IPv6 destination address
  - **VlanId**: Form: 1, Description: This property may be set in **on preStart** to select a VLAN which needs to be configured for the current bus context. Furthermore, the IL will use the first IP address of this VLAN for **ServiceDiscovery** and application endpoints that are created by [SomeIpOpenLocalApplicationEndpoint](../../SOMEIPIL/Functions/CAPLfunctionSomeIpOpenLocalApplicationEndpoint.md).
  - **UseSD**: Default Value: 1, Form: 1, Description: May be set to zero before service instances and event groups are created which should not be registered to the service discovery. **Note**: Only for services, which created with CAPL API, not by database.
  - **SendMagicCookie**: Default Value: 1, Form: 1, Description: Enable sending of magic cookie for TCP connections. If enabled, the magic cookie (message ID FFFF0000h or FFFF8000h) is sent every 10 seconds.
  - **SDDefaultUnicastOptionIp**: Form: 1, Description: Sets the default unicast IP address for the **SD IP Endpoint Option** within subscribe messages. If set it’s the IP address that will be sent in Subscribe messages of multicast only service consumers as the **Unicast IP Endpoint Option**.
  - **SDDefaultUnicastOptionPort**: Form: 1, Description: Sets the default Port Number for the **SD IP Endpoint Option** within subscribe messages. If set it’s the Port that will be sent in subscribe messages of multicast only service consumers as the **Unicast IP Endpoint Option**.
  - **DisableTxCallbackForTP**: Default Value: 0, Form: 1, Description: If set to **1**, [OnSomeIpProcessTxMessage](../../SOMEIPIL/Functions/CAPLfunctionOnSomeIpProcessTxMessage.md) callback will not be called for SOME/IP-TP messages too. It will be called before segmentation, so not for every TP segment.
  - **DetermineTCPRoleByConsumerProvider**: Form: 1, Description: If true the TCP role is set by the consumer provider.
  - **VlanPriority**: Form: 1, Description: Sets the Vlan priority.
  - **MaxSDMessageLength**: Form: 1, Description: Sets a maximum length for the SOME/IP SD message.
  - **SignalUpdateDelayInNs**: Form: 1, Description: Sets a delay for updating signals.
  - **MaxTCPRetries**: Form: 1, Description: Sets a limit for TCP connection retries.
  - **MajorVersion**: Default Value: 1, Form: 2, Description: Major version of the implemented interface
  - **MinorVersion**: Default Value: 0, Form: 2, Description: Minor version of the implemented interface
  - **SDCyclicOfferDelay**: Default Value: 1000, Form: 2, Description: Cycle time in ms
  - **SDConfigurationString**: Form: 3, Description: Transmitted as option with OfferService.
  - **SDEndpointOption**: Form: 6, Description: Sets an Ip SD endpoint option. It can be Type 0x24 for Ipv4 address and Type 0x26 for an Ipv6 address.
  - **SDCyclicRequestDelay**: Default Value: 1000, Form: 2, Description: Cycle time in ms
  - **MulticastIp**: Default Value: 239.192.255.251, Form: 2, Description: Events of this EventGroup are sent to this Multicast IPv4 address
  - **MulticastIpv6**: Form: 3, Description: Events of this EventGroup are sent to this Multicast IPv6 address
  - **MulticastPort**: Default Value: 30490, Form: 2, Description: Events of this EventGroup are sent to this Multicast port
  - **UnicastLimit (deprecated)**: Default Value: 0, Form: 2, Description:
    - 0: only multicast.
    - 1: the first client will be served by unicast and as soon as a second client arrives both will be served by multicast.
  - **MulticastThreshold**: Default Value: 0, Form: 2, Description:
    - 0: only unicast will be used.
    - 1: the first client will be already served by multicast.
    - 2: the first client will be served with unicast and as soon as the second client arrives both will be served by multicast.
    - n: the n-1 first clients will be served with unicast and as soon as the nth client arrives all will be served by multicast.
  - **CycleTimeMs**: Default Value: 0, Form: 2, Description: Strictly speaking, an Event is NEVER sent cyclically, but for test purposes it is sometimes practical for generating traffic.
  - **AliveCounterIncrementationOn**: Default Value: 1, Form: 2, Description: If the value is set to 1, an Alive counter that is responsible for a message is incremented on sending this message and transmitted with this message. This property works only with manufacturer specific databases.
  - **UpdateCRCAndLengthOn**: Default Value: 1, Form: 2, Description: If the value is set to 1, the CRC value, the length and if applicable the so-called Data-ID (see AUTOSAR E2E Library specification) are adapted on sending a message. This property works only with manufacturer specific databases.
  - **E2EProfile**: Form: 3, Description: Sets E2EProfile if E2EProtection is defined in the database. Supported values are:
    - PROFILE_04
    - PROFILE_05
    - PROFILE_06
    - PROFILE_07
    - PROFILE_08
    - PROFILE_44
    - PROFILE_4m
    - PROFILE_7m
  - **E2EDataID**: Form: 2, Description: Sets E2EDataID for the provided event.
  - **TPEnable**: Default Value: 0, Form: 2, Description:
    - 0: Do not use SOME/IP-TP
    - 1: Enable SOME/IP TP
    - Note: SOME/IP-TP can only be activated if the event or method was created with SomeIpCreate...…-Functions. If the event or method was defined in database, the definition from database is used for SOME/IP-TP.
  - **TPSegmentLength**: Default Value: 1024, Form: 2, Description: Max. length of a SOME/IP-TP segment.
  - **TPSeparationTime**: Default Value: 0.01sec, Form: 2, Description: Separation time between SOME/IP-TP segments.
  - **SDTTL**: Default Value: 300, Form: 2, Description: TimeToLive in seconds
  - **SDMinInitialDelay**: Default Value: 10, Form: 2, Description: Minimum delay in ms before first message
  - **SDMaxInitialDelay**: Default Value: 30, Form: 2, Description: Maximum delay in ms before first message
  - **SDMaxRepetition**: Default Value: 3, Form: 2, Description: Number or repetitions before cyclic sending
  - **SDBaseRepetitionDelay**: Default Value: 30, Form: 2, Description: Time in ms. Delay between repetitions is then (2^#wdh)*basedelay
  - **SDMinResponseDelay**: Default Value: 10, Form: 2, Description: Minimum delay in ms before sending a response
  - **SDMaxResponseDelay**: Default Value: 30, Form: 2, Description: Maximum delay in ms before sending a response
  - **SDExplicitInitialDataControlBehavior**: Default Value: 0, Form: 2, Description: Activates/deactivates sending of the **InitialDataRequest** flag on consumer side and sending of the **InitialDataControl** flag on provider side according to R19/11 and R20/11
    - 0: Deactivates
    - 1: Activates
    - This property must be set in `on prestart`.
  - **SDSUBSCRIBE_RETRY_MAX**: Default Value: 0, Form: 2, Description: Sets the maximum number of repetitions a customer tries to subscribe after a seen offer if no acknowledgement was received.
  - **SDSUBSCRIBE_RETRY_DELAY**: Default Value: 0, Form: 2, Description: Sets the delay between the subscribes sent by a consumer if no acknowledgment was received and the max number of retries is not reached.

- **objHandle**: Handle of a service, eventgroup or event.
- **value**: New value of the property.
- **buffer**: A byte buffer containing the new value of the property.
- **bufferLength**: The size of or the number of bytes to copy from the parameter **buffer**.
- **ip_endpoint**: An ip endpoint where you can set ip address, port and transport protocol like UDP/TCP.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

- **Example form 1**: `AREthSetProperty("ClientId", 1);`

- **Example form 2**:
  
```c
  dword appEndpointHandle;
  dword serviceHandle;

  appEndpointHandle = SomeIpOpenLocalApplicationEndpoint(kUDP, 30501);
  serviceHandle  = SomeIpCreateConsumedServiceInstance(appEndpointHandle, 1 /*serviceId*/, 1 /*instanceId*/);
  AREthSetProperty(serviceHandle, "MajorVersion", 2);
  ```

- **Example form 3**:
  
  ```c
dword appEndpointHandle;
  dword serviceHandle;

  appEndpointHandle = SomeIpOpenLocalApplicationEndpoint(kUDP, 30501);
  serviceHandle = SomeIpCreateConsumedServiceInstance(appEndpointHandle, 1 /*serviceId*/, 1 /*instanceId*/);
  AREthSetProperty(serviceHandle, "SDConfigurationString","test123");

  ```

- **Example form 4**:
  
  ```c
  Byte buffer[16] = {0xFF, 0x14, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x04, 0x00, 0x01};
AREthSetProperty("SDMulticastIpv6", buffer);
  ```

- **Example form 5**:
  
  ```c
  Byte buffer[16] = {0xFF, 0x14, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x04, 0x00, 0x01};
  AREthSetProperty("SDMulticastIpv6", 16, buffer);


```

- **Example form 6**:
  
  ```c
  char serviceName[20] = "test_service";
  dword csi;
IP_Endpoint ep;

  ep = IP_Endpoint(UDP:[ff::1]:6000);
  csi = SomeIpGetProvidedObjectHandle(serviceName);
  SomeIpSDSetServiceStatus(csi, @this);
  AREthSetProperty(csi, "SDEndpointOption", ep);
  ```

[See Also](javascript:void(0);)
