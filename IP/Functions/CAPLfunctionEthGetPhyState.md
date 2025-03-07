[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthGetPhyState.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethGetPhyState**

# ethGetPhyState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note:** Please note that this functionality is hardware dependent:

- **VT6303** supports this functionality in channel-based **and** [network-based](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) access.
- The VN-family (e.g. **VN5640**) supports this functionality only in [network-based](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) access.

## Function Syntax

```plaintext
long ethGetPhyState(long channel ); // form 1
long ethGetPhyState(long channel, long hwChannel ); // form 2
long ethGetPhyState(ethernetPort port ); // form 3
```

## Description

Gets the PHY state.

**Note:**

- This function can be used only for PHY types supporting this feature like TJA-1101.
- Form 1 and form 2 is only for channel-based access.
- Form 3 is only for network-based access.

## Parameters

- **channel**: Ethernet channel number.  
  Value range: 1..32

- **hwChannel**: Hardware channel number. Vector network interface must support more than 1 hardware channel to use.  
  Value range: 1..16

- **port**: Ethernet port.  
  Only supported for [network-based](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) configurations and **physical** measurement ports.

## Return Values

- **PHY state**:
  - 1: ePhyNormalState
  - 2: ePhySleepState
  - 3: ePhyPowerOffState
  - 4: ePhySleepRequestState
  - 5: ePhySleepLocalState
  - 6: ePhySleepLocalRequestState

  **Note:** States 5 and 6 can only be get with 10Base-T1S TC10-capable modules.

- **0**: An error occurred

## Example

```plaintext
/* TC10 testing could be implemented by polling the PhyState of Ports */

on timer myTimer
{
  if (ethGetPhyState(ethernetPort::MyNetworkName::MyPortName) == 1 /*ePhyNormalState*/)
  {
    write("ethernetPort::MyNetworkName::MyPortName's PHY is operational");
  }
  if (ethGetPhyState(ethernetPort::MyNetworkName::MyPortName) == 2 /*ePhySleepState */)
  {
    write("ethernetPort::MyNetworkName::MyPortName's PHY is sleeping");
  }
  if (ethGetPhyState(ethernetPort::MyNetworkName::MyPortName) == 3 /*ePhyPowerOffState */)
  {
    write("ethernetPort::MyNetworkName::MyPortName's PHY is powered-down");
  }
}
```

[ethSetPhyState](CAPLfunctionEthSetPhyState.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)