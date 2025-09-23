[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitScopePerformSerialBitAnalysis.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitScopePerformSerialBitAnalysis

# testWaitScopePerformSerialBitAnalysis

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long testWaitScopePerformSerialBitAnalysis (linframe aMessage, dword flags, dword msgFieldStart, dword msgFieldEnd, ScopeBitMaskPolygon bitMaskPolygon, long domVoltageThreshold , long recVoltageThreshold, ScopeAnalyseHandle handle);
```

## Description

Checks the bits of a LIN message against the defined bitmask.

## Parameters

- **aMessage**: The LIN message to be analyzed.
- **flags**: Reserved must be set to 0.
- **msgFieldStart, msgFieldEnd**: The start and end of the cutout to be fitted.
- **bitMaskPolygon**: The bitmask which shall be used.

  **ScopeBitMaskPolygon Selectors**

  - **maskPointCount**: Count of the points in the mask-arrays, Type: long
  - **data_0_Mask**: Voltage level in mV for dominant bits, Type: long[]
  - **data_1_Mask**: Voltage level in mV for recessive bits, Type: long[]
  - **timeOffset**: Relative position within bit in percent, Type: double[]

- **domVoltageThreshold, recVoltageThreshold**: The voltage levels in millivolt used from the bit parser for detecting dominant and recessive bits.
- **handle**: A unique ID. The same handle must be used for all bit analysis function calls.

  **ScopeAnalyseHandle Selectors**

  - **handle**: A unique ID, Type: long

## Return Values

- **0**: No errors found
- **< 0**: Error occurred.

## Example

—
