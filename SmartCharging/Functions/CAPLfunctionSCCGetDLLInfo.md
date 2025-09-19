[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetDLLInfo.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [General Functions](../CAPLFunctionsSmartChargingOverview.md#GeneralFunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#GeneralFunctions) » **SCC_GetDLLInfo**

# SCC_GetDLLInfo

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```
dword SCC_GetDLLInfo ( dword selector )
```

## Description

Gets additional information about the DLL.

## Parameters

- **selector**: Selects the desired return value (see below).

## Return Values

- **0**: The file version of the DLL in 24 bit BCD format (supports build numbers up to 99), e.g. 0x010203 for V1.2.3.
- **1**: The major version of the DLL.
- **2**: The minor version of the DLL.
- **3**: The build number of the DLL.
- **4**: The file version of the DLL in 32 bit BCD format, e.g. 0x01020123 for V1.2.123.

## Example

—

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
