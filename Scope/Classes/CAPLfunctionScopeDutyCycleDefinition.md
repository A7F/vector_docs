[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Scope/Classes/CAPLfunctionScopeDutyCycleDefinition.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../CAPLfunctionsScopeOverview.md) » Class: scopeDutyCycleDefinition

# Class: scopeDutyCycleDefinition

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

This structure defines the threshold levels for the duty cycle measurement.

**Threshold Levels:**

- **TH<sub>Rec(max)</sub>**: Maximum voltage level of a recessive bit
- **TH<sub>Dom(max)</sub>**: Maximum voltage level of a dominant bit
- **TH<sub>Rec(min)</sub>**: Minimum voltage level of a recessive bit
- **TH<sub>Dom(min)</sub>**: Minimum voltage level of a recessive bit

## Methods

—

## Attributes

- **THDomMin**: Defines the minimal voltage level for a dominant bit level in mV.  
  **Type**: long  
  **Access Limitations**: Read/Write

- **THDomMax**: Defines the maximal voltage level for a dominant bit level in mV.  
  **Type**: long  
  **Access Limitations**: Read/Write

- **THRecMin**: Defines the minimal voltage level for a recessive bit level in mV.  
  **Type**: long  
  **Access Limitations**: Read/Write

- **THRecMax**: Defines the maximal voltage level for a recessive bit level in mV.  
  **Type**: long  
  **Access Limitations**: Read/Write

[Related Links:](../../Test/Functions/CAPLfunctionTestWaitScopePerformSerialBitAnalysis.md)  
- [testWaitScopePerformSerialBitAnalysis](../../Test/Functions/CAPLfunctionTestWaitScopePerformSerialBitAnalysis.md)  
- [testWaitScopeGetSerialBitAnalysisData](../../Test/Functions/CAPLfunctionTestWaitScopeGetSerialBitAnalysisData.md)  
- Class: scopeDutyCycleDefinition

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)