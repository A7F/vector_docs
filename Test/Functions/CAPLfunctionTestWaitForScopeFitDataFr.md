[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForScopeFitDataFr.md)

**CAPL Functions** » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitForScopeFitDataFr

# testWaitForScopeFitDataFr

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long testWaitForScopeFitDataFr(frFrame aMessage, dword msgFieldStart, dword msgFieldEnd); // form 1`
- `long testWaitForScopeFitDataFr(frFrame aMessage, dword msgFieldStart, dword msgFieldEnd, dword preTimeNs, dword postTimeNs); // form 2`

## Description

The defined frame cutout is shown in the scope's [Diagram](../../../CANoeCANalyzer/SCOPE/ScopeDiagram.md) view. The enlarged area is automatically scaled in time direction.

## Parameters

- **aMessage**: The frame to be fitted.
- **msgFieldStart, msgFieldEnd**: The start and end of the cutout to be fitted. See `<application>\Reusable\CAPL_Includes\Scope\` [ScopeBitAnalyse.cin](javascript:startDemoLoader('"Reusable\\CAPL_Includes\\Scope"')).
- **preTimeNs**: Defines the preliminary lead time in [ns] for the defined message field start.
- **postTimeNs**: Defines the overtravel time in [ns] for the defined message field end.

## Return Values

- **1**: Success
- **0**: Timeout
- **< 0**: Error occurred. See **EScopeCAPLFitDataReturnCode** in `<application>\Reusable\CAPL_Includes\Scope\` [ScopeBitAnalyse.cin](javascript:startDemoLoader('"Reusable\\CAPL_Includes\\Scope"')).

## Example

[Scope Sample Configuration](../../../SampConf/FlexRay/CANoe/Scope/FlexRayBitMaskAnalysisCANoe.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)