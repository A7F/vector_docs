[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetCertificateChainData.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Data Queries** » **Shared Functions** » **SCC_GetCertificateChainData**

# SCC_GetCertificateChainData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**

- `<InvalidValueSigned>` and/or `<InvalidValueUnsigned>` can be defined in the XML configuration.
- These are returned if an optional numeric message parameter was queried by this function but not found.
- See [Configuration of Vehicle SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) or [Configuration of Chargepoint SCC Nodes](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md).

## Function Syntax

```plaintext
void SCC_GetCertificateChainData ( long Target, char IdAttr[], long& SubCertificateCount )
```

## Description

Reads Id (to the output buffer) and number of sub certificates (via reference) of the target certificate chain. The ID is only available for **ISO 15118**.

## Parameters

- **Target**: Set this according to the type of certificate chain that is queried:
  - 0 = ContractSignatureCertChain
  - 1 = SAProvisioningCertChain (EV and ISO 15118 only)

- **IdAttr**: Queries the Id attribute of the certificate chain (to the given char buffer).

- **SubCertificateCount**: Gets the number of sub certificates (via reference).

## Return Values

—

## Example

—
