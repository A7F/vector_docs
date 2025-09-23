[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Scope/Classes/CAPLfunctionScopeFieldLengthData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../CAPLfunctionsScopeOverview.md) » Class: scopeFieldLengthData

# Class: scopeFieldLengthData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

This structure contains the common bit information for

- the field the bit is contained,
- the bit number within the field
- the length of the bit
- the absolute bit time in [ns]
- the sample point voltage
- the bit level.

## Methods

—

## Attributes

- **BitField**: The bit field where the bit is contained.  
  Type: long  
  Access Limitations: Read-only

- **BitNo**: The bit number within the field (starts with 0).  
  Type: dword  
  Access Limitations: Read-only

- **Lenghth**: The bit time in ns.  
  Type: long  
  Access Limitations: Read-only

- **StartTime**: The time the bit started in ns.  
  Type: int64  
  Access Limitations: Read-only

- **SamplePointVoltage**: The voltage of the bit at the sample point.  
  Type: long  
  Access Limitations: Read-only

- **BitLevel**:  
  0: Dominant  
  1: Recessive  
  Type: dword  
  Access Limitations: Read-only

[testWaitScopeGetFieldLengthData](../../Test/Functions/CAPLfunctionTestWaitScopeGetFieldLengthData.md)
