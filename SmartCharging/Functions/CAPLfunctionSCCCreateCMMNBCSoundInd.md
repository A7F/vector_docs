[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCMMNBCSoundInd.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Test Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » SCC_CreateCM_MNBC_Sound_Ind

# SCC_CreateCM_MNBC_Sound_Ind

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
void SCC_CreateCM_MNBC_Sound_Ind ( byte RunId[], byte SourceMac[], byte TargetMac[], dword Count )
```

## Description

Creates a **CM_MNBC_Sound.Ind** message for sending.

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMacAddress**: MAC address of sender.
- **Count**: Countdown counter for number of Sounds remaining.

### Additional Parameters

1. **ApplicationType** (dword):
   - 0x00 = PEV-EVSE Association
   - 0x01-0xFF = Reserved

2. **SecurityType** (dword):
   - 0x00 = No Security
   - 0x01 = Public Key Signature
   - 0x02-0xFF = Reserved

3. **SenderId** (byte[]): 17 byte ID

4. **Reserved field** (byte[]): 8 byte

5. **Random number** (byte[]): 16 byte, if not set a random value will be generated.

## Return Values

—

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
