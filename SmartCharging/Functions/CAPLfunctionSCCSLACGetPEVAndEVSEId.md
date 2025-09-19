[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACGetPEVAndEVSEId.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **SLAC Data Queries** » **Shared Functions** » **SCC_SLAC_GetPEVAndEVSEId**

# SCC_SLAC_GetPEVAndEVSEId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function can be called only within the assigned callback. The function is used to query the details of a request.

## Function Syntax

```
void SCC_SLAC_GetPEVAndEVSEId ( byte PEVID[], byte EVSEID )
```

## Description

Queries the PEV and EVSE IDs.

## Parameters

- **PEVID**: Queries the 17 byte PEV ID (to the given byte buffer).
- **EVSEID**: Queries the 17 byte EVSE ID (to the given byte buffer).

## Return Values

—

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
