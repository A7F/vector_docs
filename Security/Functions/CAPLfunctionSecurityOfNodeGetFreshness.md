[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityOfNodeGetFreshness.md)

## SecurityOfNodeGetFreshness

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityOfNodeGetFreshness

**Valid for:** CANoe DE • CANoe4SW DE

### Function Syntax

```
long SecurityOfNodeGetFreshness(char nodeName[], char networkName[], char freshnessIdentifierString[], dword freshnessValueId, byte freshnessData[], dword freshnessDataLength)
```

### Description

Gets the freshness value of the specified node on the specified network for the specified Id.

As freshness values differ from Security Source to Security Source, refer to the Security Source specific manual for more information about which values to specify as parameters.

You must call [SecurityLocalStartControlSimulationNode](CAPLfunctionSecurityLocalStartControlSimulationNode.md) before this callback is called.

### Parameters

- **char nodeName[]**: The name of the node.
- **char networkName[]**: The name of the network the node is on.
- **char freshnessIdentifierString[]**: A string as an identifier for the freshness to get.
- **dword freshnessValueId**: A numerical Id for the freshness to get.
- **byte freshnessData[] [In/Out]**: The buffer for the freshness to get.
- **dword freshnessDataLength [In/Out]**: The length of the buffer for the freshness to get in bytes.

### Return Values

- **1**: Success. A value of 1 means that the action was successful. A value less than or equal to 0 means error.
- **0**: Error, no details.
- **-1**: Invalid handle.
- **-2**: Data incomplete.
- **-3**: Signal length does not fit.
- **-4**: Security source error, no details.
- **-6**: Not supported.
- **-10**: Security is not usable. Reasons can be: Security Manager version is too old, Tool Version is too old, Security Profile is invalid.

### Example

—
