[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Scope/Classes/CAPLfunctionScopeSerialBitAnalysisViolationData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../CAPLfunctionsScopeOverview.md) » Class: scopeSerialBitAnalysisViolationData

# Class: scopeSerialBitAnalysisViolationData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

This structure contains the violation data for a bit.

## Methods

—

## Attributes

- **BitField**  
  The bit field e.g. LIN Sync Byte Field, of the bit used for the duty cycle measurement.  
  Type: `long`  
  Access Limitations: Read-only

- **BitNo**  
  The bit number within the field (starts with 0).  
  Type: `dword`  
  Access Limitations: Read-only

- **BitStartTime**  
  The time the bit started in ns.  
  Type: `int64`  
  Access Limitations: Read-only

- **BitLevel**  
  0: Dominant  
  1: Recessive  
  Type: `byte`  
  Access Limitations: Read-only

- **SamplePointVoltage**  
  The voltage of the bit at the sample point.  
  Type: `long`  
  Access Limitations: Read-only

- **DisturbanceTimeStart**  
  Relative time in [ns] to **BitStartTime** where the violation of the bitmask starts.  
  Type: `long`  
  Access Limitations: Read-only

- **DisturbanceStartVoltage**  
  Voltage level in [mV] on the **DisturbanceTimeStart**.  
  Type: `long`  
  Access Limitations: Read-only

- **DisturbanceTimeEnd**  
  Relative time in [ns] to **BitStartTime** where the violation of the bitmask end.  
  Type: `long`  
  Access Limitations: Read-only

- **DisturbanceEndVoltage**  
  Voltage level in [mV] on the **DisturbanceTimeEnd**.  
  Type: `long`  
  Access Limitations: Read-only

- **ScopeSamplePeriod**  
  The sample period of the scope in [ns].  
  Type: `float`  
  Access Limitations: Read-only

- **ScopeVoltageTolerance**  
  The voltage tolerance of the scope measurement probe [mV].  
  Type: `float`  
  Access Limitations: Read-only

[Related Functions](../../Test/Functions/CAPLfunctionTestWaitScopePerformSerialBitAnalysis.md) • [testWaitScopeGetSerialBitAnalyseViolationData](../../Test/Functions/CAPLfunctionTestWaitScopeGetSerialBitAnalyseViolationData.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
