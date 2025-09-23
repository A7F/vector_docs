[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetEncryptedPrivateKey.md)

# SCC_GetEncryptedPrivateKey

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » SCC_GetEncryptedPrivateKey

**Valid for**:  CANoe DE • CANoe4SW DE

**Note**  
This function can be called only within the assigned callback. The function is used to query the details of a request.

## Function Syntax

```plaintext
void SCC_GetEncryptedPrivateKey ( byte Key[], char IdAttr[] )
```

## Description

Gets the encrypted private key of the new contract certificate.

## Parameters

- **Key**  
  Queries the encrypted private key (48 byte) of the new contract certificate (to the given byte buffer).

- **IdAttr**  
  Queries the Id attribute (to the given char buffer).

## Return Values

—

## Example

—
