[PtpSetProperty](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionPtpSetProperty.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **PtpSetProperty**

# PtpSetProperty

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long PtpSetProperty(char propertyName[], int64 value); // form 1
long PtpSetProperty(char propertyName[], dword length, byte value[]); // form 2
```

## Description

The behavior of the PTP layer can be configured using properties. You can statically configure the port role of a simulated node. This function allows for configuring properties to pre-set a configuration for the time-aware end station.

For example, you can set the **PortRole** property to **SlavePort (2)** for a node in its **on prestart** CAPL event handler.

## Parameters

- **propertyName**: Name of the property to be set.
  - **PortRole**: Values (Integer):
    - 0 = Auto select (Role is selected by BMCA) (Default)
    - 1 = MasterPort
    - 2 = SlavePort
    - 3 = PassivePort
    - 4 = DisabledPort
  - **PortNumber**: Values (Integer): 1 to 65535, Default: 1
  - **LogSyncInterval**: Values (Integer): -128 to 127, Default: -3 (equates to 0.125 s)
  - **Priority1**: Values (Integer): 0 to 0xFF, Default: 0xFA
  - **ClockClass**: Values (Integer): 0 to 0xFF, Default: 0xF8
  - **ClockAccuracy**: Values (Integer): 0 to 0xFF, Default: 0xFE
  - **OffsetScaledLogVariance**: Values (Integer): 0 to 65535, Default: 1
  - **Priority2**: Values (Integer): 0 to 0xFF, Default: 0xF8
  - **VlanId**: Values (Integer):
    - 0 = No VLAN used (Default)
    - 1 to 4094 = VLAN ID
  - **VlanPriority**: Values (Integer): 0 to 7, Default: 0
  - **RequestLogSyncInterval**: This property cannot be set within the **on preStart** event handler. Values (Integer):
    - -127 to 125 = Sync interval requested.
    - 127 = Instructs the port that receives this TLV to stop sending time-synchronization event messages.
    - 126 = Instructs the port that receives this TLV to reset its current **LogSyncInterval** to the initial value.
    - -128 = Instructs the port that receives this TLV not to change the mean time interval between successive time-synchronization event messages.
  - **RequestLogPdelayReqInterval**: This property cannot be set within the **on preStart** event handler. Values (Integer):
    - -127 to 125 = Propagation delay request interval requested.
    - 127 = Instructs the port that receives this TLV to stop sending link delay measurement messages.
    - 126 = Instructs the port that receives this TLV to reset its current **LogPdelayReqInterval** to the initial value.
    - -128 = Instructs the port that receives this TLV not to change the mean time interval between successive propagation delay request messages.
  - **RequestLogAnnounceInterval**: This property cannot be set within the **on preStart** event handler. Values (Integer):
    - -127 to 125 = Announce interval requested.
    - 127 = Instructs the port that receives this TLV to stop sending announce messages.
    - 126 = Instructs the port that receives this TLV to reset its current **LogAnnounceInterval** to the initial value.
    - -128 = Instructs the port that receives this TLV not to change the mean time interval between successive announce messages.
  - **DestinationAddress**: Sets the destination MAC address of PTP messages originating from the node. The function overload with the byte array type for the value parameter must be used. Set the **length** parameter to 6 and **value** parameter to the address in network byte order. If this property is not set, the default address 01:80:C2:00:00:0E will be used.
  - **LogPdelayReqInterval**: Values (Integer): -128 to 127, Default: 0 (equates to 1 s)
  - **LogAnnounceInterval**: Values (Integer): -128 to 127, Default: 0 (equates to 1 s)
  - **StartTime**: Values: 0 to 0x7FFFFFFFFFFFFFFF, Unit: ns (nanoseconds)

- **value**: New value of the property.
- **length**: Size of the property (Array) in bytes.

## Return Values

- **0**: The function succeeded.
- **≠0**: Error code

## Example

```plaintext
on preStart
{
  // Sets the port role to slave
  if (PtpSetProperty("PortRole", 2) != 0)
  {
    Stop();
    return;
  }
}
```