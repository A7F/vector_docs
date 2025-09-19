[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthGetEthernetPortInfos.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethGetEthernetPortInfos

# ethGetEthernetPortInfos

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ethGetEthernetPortInfos (ethernetportinfo portInfos[]);
```

## Description

Retrieves port related information of all connected network-based Ethernet devices.

You must provide an array of **ethernetPortInfo** elements of sufficient size for all available hardware ports.

## Parameters

- **portInfos**: Array of type **`<ethernetPortInfo>`**, which contains the retrieved hardware info as a struct with the following members:
  - `char PortName[32]`
  - `char NetworkName[32]`
  - `char SegmentName[32]`
  - `uint32_t IsPhysical`

## Return Values

Number of valid **ethernetPortInfo** elements (0 in case of any error).

## Example

```plaintext
on key 'C'  // retrieve complete hardware info
{
  ethernetportinfo  allPorts[128];
  long numPorts, j;
  numPorts = ethGetEthernetPortInfos(allPorts);
  write("Found hardware info of %d ports ", numPorts);
  for (j=0; j < numPorts; j++)
  {
    write("#%d %s::%s::%s isPhy:%d", j,
          allPorts[j].NetworkName,
          allPorts[j].SegmentName,
          allPorts[j].PortName,
          allPorts[j].IsPhysical);
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
