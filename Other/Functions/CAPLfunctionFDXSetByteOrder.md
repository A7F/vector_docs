[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionFDXSetByteOrder.md)

# FDXSetByteOrder

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » FDXSetByteOrder

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long FDXSetByteOrder(long fdxClientHandle, long byteOrder);
```

## Description

This function configures the byte order of the FDX protocol that should be used for the communication with the specified client. The default is Little Endian.

**Note**: With each received FDX datagram, your CANoe DE product automatically takes over the byte order from the datagram for the further communication with this client. The function `FDXSetByteOrder` is therefore only relevant in the rare case that CANoe DE product should send datagrams to an FDX client without having received a datagram from this client.

## Parameters

- **fdxClientHandle**: FDX client for which the byte order should be set.
- **byteOrder**:
  - 1: Little Endian
  - 2: Big Endian

## Return Values

- **0**: Successful function call
- **-1**: The parameter `fdxClientHandle` is invalid.
- **-1**: The parameter `byteOrder` is invalid.

## Example

[Coupling of two CANoe Instances using the FDX Protocol](../../../CANoeCANalyzer/Interfaces/FDXProtocolCouplingCANoeInstances.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)