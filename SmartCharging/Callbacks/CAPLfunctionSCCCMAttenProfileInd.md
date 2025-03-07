[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCMAttenProfileInd.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » SCC_CM_Atten_Profile_Ind

# SCC_CM_Atten_Profile_Ind

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
void SCC_CM_Atten_Profile_Ind ( byte RunId[], 
byte SourceMacAddress[], byte PEVMAC[], 
dword NumGroups, byte AAG[] )
```

## Description

The callback is called as soon as a **CM_Atten_Profile.Ind** message is received.

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMacAddress**: MAC address of sender.
- **PEVMAC**: MAC Address of the vehicle.
- **NumGroups**: Number of attenuation groups.
- **AAG**: Average Attenuation Group (array length is indicated by the parameter **NumGroups**).

## Return Values

—

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)