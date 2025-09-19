[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionFDXSetProtocolVersion.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » FDXSetProtocolVersion

# FDXSetProtocolVersion

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long FDXSetProtocolVersion(long fdxClientHandle, byte majorVersion, byte minorVersion);
```

## Description

This function configures the version of the FDX protocol that should be used for the communication with the specified client.

**Note**  
With each received FDX datagram, CANoe DE product automatically adapts to the protocol version from the received datagram. The function `FDXSetProtocolVersion` is therefore only relevant in the rare case that CANoe DE product should send datagrams to an FDX client without having received a datagram from this client.

## Parameters

- **fdxClientHandle**: FDX client for which the protocol version should be set.
- **majorVersion**: Major version of the FDX protocol
- **minorVersion**: Minor version of the FDX protocol

## Return Values

- **0**: Successful function call
- **-1**: The parameter `fdxClientHandle` is invalid.
- **-2**: The given main version (`majorVersion` parameter) is not supported by CANoe DE product.

## Example

```plaintext
// Configure FDX protocol version 1.2 for the given client
FDXSetProtocolVersion(fdxClientHandle, 1, 2);

// Configure FDX protocol version 2.0 for the given client
FDXSetProtocolVersion(fdxClientHandle, 2, 0);
```

See also: [Coupling of two CANoe Instances using the FDX Protocol](../../../CANoeCANalyzer/Interfaces/FDXProtocolCouplingCANoeInstances.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
