[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACSetAttenuation.md)

**CAPL Functions » Smart Charging » SCC Modeling Libraries (Simulation Setup) » SLAC Simulation » EVSE Functions » SCC_SLAC_SetAttenuation**

# SCC_SLAC_SetAttenuation

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_SLAC_SetAttenuation(float AttenuationMean, float AttenuationDev)
```

## Description

Changes the probability distribution used to create attenuation characteristics when simulating a HomePlug Green PHY chip. The values apply to all SLAC sessions, yet may be set each time an M-Sound is received using the indication [SCC_CM_MNBC_Sound_Ind](../Callbacks/CAPLfunctionSCCCMMNBCSoundInd.md).

## Parameters

- **AttenuationMean**: Attenuation Mean Value in dB.
- **AttenuationDev**: Standard deviation of the distribution in dB.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)