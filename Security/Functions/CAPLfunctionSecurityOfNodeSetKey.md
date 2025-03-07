[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityOfNodeSetKey.md)

## SecurityOfNodeSetKey

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityOfNodeSetKey

**Valid for**: [CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

### Function Syntax

```
long SecurityOfNodeSetKey(char nodeName[], char networkName[], char keyIdentifierString[], dword keyIdentifierValue, byte newKey[], dword keyLength, dword flags)
```

### Description

Changes a key at the node the specified node on the specified network.

As keys and the key handling differs from Security Source to Security Source you have to refer to the Security Source specific manual to get more information about which values you have to specify as parameters.

You have to call [SecurityLocalStartControlSimulationNode](CAPLfunctionSecurityLocalStartControlSimulationNode.md) before this callback is called.

### Parameters

- **char nodeName[]**: The name of the node.
- **char networkName[]**: The name of the network the node is on.
- **char keyIdentifierString[]**: A string as an identifier for the key to set.
- **dword keyIdentifierValue**: A numerical Id for the key to set.
- **byte newKey[]**: The key to set as a byte array.
- **dword keyLength**: The length of the new key in bytes.
- **dword flags**: Reserved. (set to 0)

### Return Values

- **1**: Success. A Value of 1 means that the action was successful. A value less than or equal to 0 means error.
- **0**: Error, no details.
- **-1**: Invalid handle.
- **-2**: Data incomplete.
- **-3**: Signal length does not fit.
- **-4**: Security source error, no details.
- **-6**: Not supported.
- **-10**: Security is not usable. Reasons can be: Security Manager version is too old. Tool Version is too old. Security Profile is invalid.

### Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)