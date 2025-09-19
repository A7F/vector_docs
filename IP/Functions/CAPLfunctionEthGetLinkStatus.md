[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthGetLinkStatus.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethGetLinkStatus**

# ethGetLinkStatus

[Valid for: CANoe DE • CANoe4SW DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

- `long ethGetLinkStatus( long channel ); // form 1`
- `long ethGetLinkStatus( long channel, long hwChannel ); // form 2`
- `long ethGetLinkStatus( ethernetPort port ); // form 3`

## Description

Returns the link status of the channel.

## Parameters

- **channel**: Ethernet channel number. Value range: 1..32
- **hwChannel**: Hardware channel number. Vector network interface must support more than 1 hardware channel to use. Value range: 1..16
- **port**: Ethernet port, described by network name and port name.

## Return Values

- **0**: Link down
- **1**: Link up
- **-1**: Read link status failed

## Example

**Example 1**

```plaintext
on key 'i'
{
  write("Link status has the value: %d", ethGetLinkStatus(1));
}
```

**Example 2**

```plaintext
on key 'i'
{
  write("Link status has the value: %d", ethGetLinkStatus(ethernetPort::MyNetworkName::MyPortName));
}
```

[See Also](javascript:void(0);)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
