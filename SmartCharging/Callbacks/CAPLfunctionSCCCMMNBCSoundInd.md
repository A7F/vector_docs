[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCMMNBCSoundInd.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » **SCC_CM_MNBC_Sound_Ind**

# SCC_CM_MNBC_Sound_Ind

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**

This indication can be used to set individual attenuation values for different vehicles. To implement this, call [SCC_SLAC_SetAttenuation](../Functions/CAPLfunctionSCCSLACSetAttenuation.md) with values depending on the remote MAC address or the RunID of the process.

## Function Syntax

```plaintext
void SCC_CM_MNBC_Sound_Ind ( byte RunId[], byte SourceMacAddress[], dword Count )
```

## Description

The callback is called as soon as a **CM_MNBC_Sound.Ind** message is received.

Further details that are transmitted in this request can be queried with the following functions:

- [SCC_SLAC_GetApplicationType](../Functions/CAPLfunctionSCCSLACGetApplicationType.md)
- [SCC_SLAC_GetSecurityType](../Functions/CAPLfunctionSCCSLACGetSecurityType.md)
- [SCC_SLAC_GetSourceId](../Functions/CAPLfunctionSCCSLACGetSourceId.md)
- [SCC_SLAC_GetRandomValue](../Functions/CAPLfunctionSCCSLACGetRandomValue.md)

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMacAddress**: MAC address of sender.
- **Count**: Countdown counter for number of Sounds remaining.

## Return Values

—

## Example

—

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
