[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCMStartAttenCharInd.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **EVSE Callback Functions** » **SCC_CM_Start_Atten_Char_Ind**

# SCC_CM_Start_Atten_Char_Ind

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CM_Start_Atten_Char_Ind ( byte RunId[], 
byte SourceMacAddress[], dword NumSounds, 
dword TimeOut, byte ForwardingSTA[] )
```

## Description

The callback is called as soon as a **CM_Start_Atten_Char.Ind** message is received.

Further details that are transmitted in this request can be queried with the following functions:

- [SCC_SLAC_GetApplicationType](../Functions/CAPLfunctionSCCSLACGetApplicationType.md)
- [SCC_SLAC_GetSecurityType](../Functions/CAPLfunctionSCCSLACGetSecurityType.md)
- [SCC_SLAC_GetRespType](../Functions/CAPLfunctionSCCSLACGetRespType.md)

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMacAddress**: MAC address of sender.
- **NumSounds**: Number of M-Sounds transmitted during the SLAC process.
- **TimeOut**: Timeout for transmission of M-Sounds in multiple of 100ms.
- **ForwardingSTA**: MAC address where the measurement results shall be sent to.

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
