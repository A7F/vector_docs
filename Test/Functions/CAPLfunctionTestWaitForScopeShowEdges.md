[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForScopeShowEdges.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitForScopeShowEdges

# testWaitForScopeShowEdges

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

`long testWaitForScopeShowEdges(linFrame aMessage, dword msgFieldStart,long bitNo, long noOfBits, dword flags, ScopeanalyseHandle handle);`

## Description

The defined frame cutout of the previously transition time measurement frame together with a bitmask is shown in the scope's [Diagram](../../../CANoeCANalyzer/SCOPE/ScopeDiagram.md) view. The bitmask is only shown if the parameter **flags** is correctly defined. The enlarged area is automatically scaled in time direction.

## Parameters

- **aMessage**: The message to be fitted.
- **msgFieldStart**: The start of the cutout to be displayed. See `<application>\Reusable\CAPL_Includes\Scope\` [ScopeBitAnalyse.cin](javascript:startDemoLoader('"Reusable\\CAPL_Includes\\Scope"')).
- **startBitNo**: A bit index in the message field.
- **noOfBits**: Count of bits to be displayed.
- **flags**:
  - **Bits**:
    - 0: Bit visible for analyzed edges
      - 0 = Without bitmask
      - 1 = With bitmask
  - All other bits are reserved and must be set to 0.
- **handle**: A unique ID. Must be the same handle used by the call of the function [testGetWaitScopeSignalTransitionTime](CAPLfunctionTestGetWaitScopeSignalTransitionTime.md).

## Return Values

- **1**: Success
- **0**: Timeout
- **< 0**: Error occurred. See **EScopeCAPLFitDataReturnCode** in `<application>\Reusable\CAPL_Includes\Scope\` [ScopeBitAnalyse.cin](javascript:startDemoLoader('"Reusable\\CAPL_Includes\\Scope"')).

## Example

[Scope Sample Configuration](../../../SampConf/CAN/CANoe/Scope/BitmaskAnalysisCAN.md)
