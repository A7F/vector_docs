[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthSetLinkStatus.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethSetLinkStatus**

# ethSetLinkStatus

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long ethSetLinkStatus( long channel, long status ); // form 1`
- `long ethSetLinkStatus( long channel, long hwChannel, long status ); // form 2`
- `long ethSetLinkStatus( ethernetPort port, long status ); // form 3`

## Description

Configures the channel of the Vector hardware to establish or terminate a link.

## Parameters

- **channel**: Ethernet channel number.  
  Value range: 1..32

- **status**:  
  - 0 = link down
  - 1 = link up

- **hwChannel**: Hardware channel number. Vector network interface must support more than 1 hardware channel to use.  
  Value range: 1..16

- **port**: Ethernet port, described by network name and port name.  
  Only supported for [network-based](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) configurations and **physical** measurement ports.

## Return Values

- **0**: Success
- **1**: Invalid channel
- **2**: Read configuration failed
- **3**: Link down failed
- **4**: Link up failed
- **5**: Restore bypass failed
- **6**: Invalid link state

## Example

**Example 1**

```plaintext
//link up
on key 'u'
{
  ethSetLinkStatus(1, 1);
}

//link down
on key 'd'
{
  ethSetLinkStatus(1, 0);
}
```

**Example 2**

```plaintext
on key 'u'
{
  ethSetLinkStatus(ethernetPort::MyNetworkName::MyPortName, 1);
}
```

[See Also](javascript:void(0);)