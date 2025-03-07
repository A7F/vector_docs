[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACGetDestinationAddress.md)

## SCC_SLAC_GetDestinationAddress

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Data Queries](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_GetDestinationAddress

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
void SCC_SLAC_GetDestinationAddress ( byte[] MACAddress )
```

### Description

Gets the destination MAC address of a SLAC message to the output buffer.

**Note**: The destination address may differ from the simulation node’s address when the node is in passive mode. This function is intended to allow filtering for the node’s address in this case.

### Parameters

- **MACAddress**: Queries the destination address of the MME frame (to the given byte buffer).

### Return Values

—

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)