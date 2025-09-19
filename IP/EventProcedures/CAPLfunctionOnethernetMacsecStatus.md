[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/EventProcedures/CAPLfunctionOnethernetMacsecStatus.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **on ethernetMacsecStatus**

# on ethernetMacsecStatus

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This procedure can only be used in [network-based configurations](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md).

## Function Syntax

- `on ethernetMacsecStatus *; // form 1`
- `on ethernetMacsecStatus ethernetPort::<Network>::<PortName>; // form 2`

## Description

This event procedure is called when the Ethernet MACsec connection state of a physical port has changed. To access the control information, use the selectors. The keyword `this` is available in this procedure to access the status information.

## Parameters

- **ethernetPort::`<NetworkName>::<PortName>`**: Ethernet port qualification.

## Selectors

- **status**: The current status.
  - **Value**: Meaning
    - `0`: kMacSecStateUnknown
    - `1`: kMacSecStateUp
    - `2`: kMacSecStateDown
    - `3`: kMacSecTxSaAdded
    - `4`: kMacSecTxSaRemoved
    - `5`: kMacSecTxSaEnabled
    - `6`: kMacSecTxSaDisabled
    - `7`: kMacSecRxSaAdded
    - `8`: kMacSecRxSaRemoved
    - `9`: kMacSecRxSaEnabled
    - `10`: kMacSecRxSaDisabled
  - **Type**: enum ethernetMacsecState
  - **Access Limitation**: Read only

- **msgChannel**: Application channel, i.e. Eth 1
  - **Type**: word
  - **Access Limitation**: Read only

- **sciAddr**: The secure channel id address
  - **Type**: byte[6]
  - **Access Limitation**: Read only

- **sciPort**: The secure channel id port
  - **Type**: word
  - **Access Limitation**: Read only

- **AN**: The association number
  - **Type**: byte
  - **Access Limitation**: Read only

- **hwPort**: Port used for network-based access
  - **Type**: ethernetPort
  - **Access Limitation**: Read only

- **time_ns**: Timestamp of the status change
  - **Type**: int64
  - **Access Limitation**: Read only

## Example

—

[See Also](javascript:void(0);)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
