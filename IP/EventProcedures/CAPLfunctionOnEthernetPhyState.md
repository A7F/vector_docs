[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/EventProcedures/CAPLfunctionOnEthernetPhyState.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **on ethernetPhyState**

# on ethernetPhyState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This callback is only available in [network-based configurations](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md).

## Function Syntax

- `on ethernetPhyState *; // form 1`
- `on ethernetPhyState ethernetPort::<NetworkName>::<PortName>; // form 2`

## Description

The event procedure is called on the change of the state of an Ethernet PHY or if a relevant PHY activity has been triggered. To access the control information you would use selectors. The key word [this](../../Other/EventProcedures/CAPLfunctionKeywordThis.md) is available within an `on ethernetPhyState` procedure, to access the information of the PHY state and event type.

## Parameters

- **ethernetPort::<NetworkName>::<PortName>**: Ethernet port qualification.

## Selectors

- **hwPort**: Port associated with the PHY. Type: `ethernetPort`. Access Limitation: [network-based](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) access only.
- **time_ns**: Time stamp of the PHY event. Type: `int64`. Access Limitation: read only.
- **phystate**: 
  - 1: Normal state
  - 2: Sleep state
  - 3: PowerOff state
  - 4: SleepRequest state
  - 5: ePhySleepLocalState
  - 6: ePhySleepLocalRequestState
  Type: `int32`. Access Limitation: read only.
- **eventtype**: 
  - 1: Sleep received
  - 2: Sleep sent
  - 3: Sleep abort
  - 4: Sleep ACK received
  - 5: Sleep forwarded
  - 8: Wakeup received
  - 9: Wakeup sent
  - 10: Wakeup forwarded
  - 17: Power Off
  - 18: Power On
  - 25: PHY activated
  - 26: Sleep confirmed
  - 27: Local Sleep Requested
  Type: `int32`. Access Limitation: read only.

## Example

```plaintext
on ethernetPhyState *
{
  ethernetport myPort;
  myPort = this.hwPort;
  switch(this.phyState)
  {
    case 1:
      write("Ethernet PHY on %s is in normal state", this.name);
      break;
    case 2:
      write("Ethernet PHY on %s is in sleep state", this.portname);
      break;
    case 3:
      write("Ethernet PHY %s of segment %s is in powerOff state",
      myPort.name, myPort.segmentName);
      break;
    case 4:
      write("Ethernet PHY on %s is in sleep_request state", myPort.name);
      break;
  }
}
```

[ethGetPhyState](../Functions/CAPLfunctionEthGetPhyState.md) • [ethSetPhyState](../Functions/CAPLfunctionEthSetPhyState.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)