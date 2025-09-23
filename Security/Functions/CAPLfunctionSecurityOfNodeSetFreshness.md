# SecurityOfNodeSetFreshness

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long SecurityOfNodeSetFreshness(char nodeName[], char networkName[], char freshnessIdentifierString[], dword freshnessValueId, byte freshnessData[], dword freshnessDataLength, dword flags)
```

## Description

Sets the freshness value of the specified node on the specified network for the specified Id.

As freshness values differ from Security Source to Security Source, refer to the Security Source specific manual for more information about which values to specify as parameters.

You have to call [SecurityLocalStartControlSimulationNode](CAPLfunctionSecurityLocalStartControlSimulationNode.md) before this callback is called.

## Parameters

- **char nodeName[]**: The name of the node.
- **char networkName[]**: The name of the network the node is on.
- **char freshnessIdentifierString[]**: A string as an identifier for the freshness to set.
- **dword freshnessValueId**: A numerical Id for the freshness to set.
- **byte freshnessData[]**: The freshness to set as a byte array.
- **dword freshnessDataLength**: The length of the freshness to set in bytes.
- **dword flags**: Optional flags (depending on the Security Source).

## Return Values

A Value of 1 means that the action was successful. A value less than or equal to 0 means error.

- **1**: Success.
- **0**: Error, no details.
- **-1**: Invalid handle.
- **-2**: Data incomplete.
- **-3**: Signal length does not fit.
- **-4**: Security source error, no details.
- **-6**: Not supported.
- **-10**: Security is not usable. Reasons can include: Security Manager version is too old, Tool Version is too old, Security Profile is invalid.

## Example

—
