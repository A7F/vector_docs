[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetNetworkName.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » GetNetworkName

# GetNetworkName

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GetNetworkName(dword busType, dword channelNumber, char name[]);
```

## Description

Retrieves the name assigned in the Simulation Setup for a specific channel.

## Parameters

- **busType**: Bus system of the channel. The predefined enum BusType should be used for the value of this parameter.
- **channelNumer**: Number of the channel for the specified bus. Channel numbering starts with 1.
- **name**: Receives the name for the channel.

## Return Values

- **0**: success
- **1**: invalid bus system or channel number
- **2**: name contains characters which can’t be represented in the current CAPL string encoding
- **3**: name buffer is too small for the name

## Example

```plaintext
stack char networkName[50];
stack long ret;
ret = GetNetworkName(eCAN, 1, networkName);
write("Name of CAN 1 is: %s", networkName);
```

[GetBusNameContext](CAPLfunctionGetBusNameContext.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)