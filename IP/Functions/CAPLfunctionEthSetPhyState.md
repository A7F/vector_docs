[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthSetPhyState.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethSetPhyState**

# ethSetPhyState

**Valid for**: CANoe DE • CANoe4SW DE

**Note:** Please note that this functionality is hardware dependent:
- **VT6303** supports this functionality in channel-based **and** [network-based](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) access.
- The VN-family (e.g. **VN5640**) supports this functionality only in [network-based](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) access.

## Function Syntax

```plaintext
long ethSetPhyState(long channel, long phyState ); // form 1
long ethSetPhyState(long channel, long hwChannel, long phyState ); // form 2
long ethSetPhyState(ethernetPort port, long phyState ); // form 3
```

## Description

Sets the PHY state.

**Note:**
- This function can be used only for PHY types supporting this feature like TJA-1101.
- Form 1 and form 2 is only for channel-based access.
- Form 3 is only for network-based access.
- TC10 Sleep/Wakeup events can be sent with this function.

## Parameters

- **channel**: Ethernet channel number. Value range: 1..32
- **phyState**:
  - 1: ePhyNormalState
  - 2: ePhySleepState
  - 3: ePhyPowerOffState
  - 5: ePhySleepLocalState

  **Note:** State 5 can only be set with 10Base-T1S TC10-capable modules.

- **hwChannel**: Hardware channel number. Vector network interface must support more than 1 hardware channel to use. Value range: 1..16
- **port**: Ethernet port. Only supported for [network-based](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) configurations and **physical** measurement ports.

## Return Values

- **0**: Success
- **1**: Invalid channel or port.
- **2**: Failed

## Example

```plaintext
on key 's'
{
  ethSetPhyState(ethernetPort::MyNetworkName::MyPortName, 2 /*ePhySleepState*/);
}

on key 'n'
{
  ethSetPhyState(ethernetPort::MyNetworkName::MyPortName, 1 /*ePhyNormalState*/);
}
```

[ethGetPhyState](CAPLfunctionEthGetPhyState.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
