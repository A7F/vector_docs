[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetDHPublicKey.md)

### SCC_GetDHPublicKey

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » SCC_GetDHPublicKey

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**  
This function can be called only within the assigned callback. The function is used to query the details of a request.

### Function Syntax

```plaintext
void SCC_GetDHPublicKey ( byte Key[], char IdAttr[] )
```

### Description

Reads the Diffie-Hellman parameter (public key) from a Certificate Installation/Update Response or a Certificate Installation/Update Request (the latter only for versions other than ISO 15118).

### Parameters

- **Key**: Queries the value of element DHPublicKey (ISO 15118) resp. DHParams (other versions) (to the given byte buffer).
- **IdAttr**: Queries the ID attribute of DHPublicKey (ISO 15118 only) (to the given char buffer).

### Return Values

—

### Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
