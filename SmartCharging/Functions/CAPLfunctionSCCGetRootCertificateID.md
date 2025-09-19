[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetRootCertificateID.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEVSE) » **SCC_GetRootCertificateID**

# SCC_GetRootCertificateID

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
This function can be called only within the assigned callback. The function is used to query the details of a request.

## Function Syntax

```plaintext
void SCC_GetRootCertificateID ( long Index,
char IdOrIssuer [], byte SerialNumber[],
long& SerialNumberLength )
```

## Description

Gets the content of the **RootCertificateID** element with the specified index.

## Parameters

- **Index**: Selected index of the target RootCertificateID (index < GetNumberOfRootCertificateIDs()).

- **IDOrIssuer**:  
  - **For ISO 15118**: Queries the X509IssuerName of the target RootCertificate (to the given char buffer).
  - **Else**: Queries the RootCertificateId (to the given char buffer).

- **SerialNumber**:  
  - **For ISO 15118**: Queries the X509SerialNumber of the target RootCertificate (to the given byte buffer).
  - **Else**: Unused

- **SerialNumberLength**:  
  - **For ISO 15118**: Gets the Byte length of X509SerialNumber (via reference).
  - **Else**: Unused

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
