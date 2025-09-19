[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Scope/Classes/CAPLfunctionScopeBitDataDutyCycle.md)

## CAPL Functions » Scope » Class: scopeBitDataDutyCycle

### Valid for: CANoe DE • CANoe:lite DE

This structure contains all relevant values to measure a duty cycle within a frame. The following figure shows the parameters needed to measure the duty cycle.

For measure the duty cycle a dominant->recessive->dominant or recessive->dominant->recessive bit pattern is needed. Only in this case it is possible to measure the needed time values for the duty cycle. The different thresholds (TH`<sub>`Rec(max)`</sub>`, TH`<sub>`Dom(max)`</sub>`,TH`<sub>`Rec(min)`</sub>`,TH`<sub>`Dom(min)`</sub>`) can be defined with the structure [ScopeDutyCycleDefinition](CAPLfunctionScopeDutyCycleDefinition.md).

The calculation of the duty cycle for a bus system can differ. For e.g. LIN the minimal duty cycle is defined as DutyCycleMin = tBusMin / 2*tBit and the maximum duty cycle is defined as DutyCycleMax = tBusMax / 2 * tBit for a recessive bit. The interpretation of the calculated values depends on the physical layer specification.

### Methods

—

### Attributes

- **Keyword**: BitField
  - **Description**: The bit field e.g. LIN Sync Byte Field, of the bit used for the duty cycle measurement.
  - **Type**: long
  - **Access Limitations**: Read-only

- **Keyword**: BitNo
  - **Description**: The bit number within the field (starts with 0).
  - **Type**: dword
  - **Access Limitations**: Read-only

- **Keyword**: BitStartTime
  - **Description**: The time the bit started in ns.
  - **Type**: int64
  - **Access Limitations**: Read-only

- **Keyword**: BitLevel
  - **Description**:
    - 0: Dominant
    - 1: Recessive
  - **Type**: byte
  - **Access Limitations**: Read-only

- **Keyword**: SamplePointVoltage
  - **Description**: The voltage of the bit at the sample point.
  - **Type**: long
  - **Access Limitations**: Read-only

- **Keyword**: TDomMinOffset
  - **Description**: Relative time in ns to **BitStartTime** where the voltage equals to **THDomMin**.
  - **Type**: long
  - **Access Limitations**: Read-only

- **Keyword**: TDomMaxOffset
  - **Description**: Relative time in ns to **BitStartTime** where the voltage equals to **THDomMax**.
  - **Type**: long
  - **Access Limitations**: Read-only

- **Keyword**: TRecMinOffset
  - **Description**: Relative time in ns to **BitStartTime** where the voltage equals to **THRecMin**.
  - **Type**: long
  - **Access Limitations**: Read-only

- **Keyword**: TRecMaxOffset
  - **Description**: Relative time in ns to **BitStartTime** where the voltage equals to **THRecMax**.
  - **Type**: long
  - **Access Limitations**: Read-only

- **Keyword**: TBusMax
  - **Description**: The maximal time of the bit.
  - **Type**: long
  - **Access Limitations**: Read-only

- **Keyword**: TBusMin
  - **Description**: The minimal time of the bit.
  - **Type**: long
  - **Access Limitations**: Read-only

- **Keyword**: ScopeSamplePeriod
  - **Description**: The sample period of the scope in [ns].
  - **Type**: float
  - **Access Limitations**: Read-only

- **Keyword**: ScopeVoltageTolerance
  - **Description**: The voltage tolerance of the scope measurement probe [mV].
  - **Type**: float
  - **Access Limitations**: Read-only

### Related Links

- [testWaitScopePerformSerialBitAnalysis](../../Test/Functions/CAPLfunctionTestWaitScopePerformSerialBitAnalysis.md)
- [testWaitScopeGetSerialBitAnalysisData](../../Test/Functions/CAPLfunctionTestWaitScopeGetSerialBitAnalysisData.md)
- [Class: scopeDutyCycleDefinition](CAPLfunctionScopeDutyCycleDefinition.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
