[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForScopeFitData.md)

**CAPL Functions** » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitForScopeFitData

# testWaitForScopeFitData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long testWaitForScopeFitData(message aMessage, dword msgFieldStart, dword msgFieldEnd); // form 1`
- `long testWaitForScopeFitData(message aMessage, dword msgFieldStart, dword msgFieldEnd, dword preTimeNs, dword postTimeNs); // form 2`
- `long testWaitForScopeFitData(linFrame aMessage, dword msgFieldStart, dword msgFieldEnd); // form 3`
- `long testWaitForScopeFitData(linFrame aMessage, dword msgFieldStart, dword msgFieldEnd, dword preTimeNs, dword postTimeNs); // form 4`
- `long testWaitForScopeFitData(message aMessage, dword msgFieldStart, dword msgFieldEnd, dword flags); // form 5`

## Description

The defined frame cutout is shown in the scope's [Diagram](../../../CANoeCANalyzer/SCOPE/ScopeDiagram.md) view. The enlarged area is automatically scaled in time direction.

## Parameters

- **aMessage**: The message to be fitted.
- **msgFieldStart, msgFieldEnd**: The start and end of the cutout to be fitted.
- **preTimeNs**: Defines the preliminary lead time in [ns] for the defined message field start.
- **postTimeNs**: Defines the overtravel time in [ns] for the defined message field end.
- **flags**: Defines the signals which should be displayed.
  - **Bits**:
    - 0: 0 - CAN high signal not visible, 1 - CAN high signal visible
    - 1: 0 - CAN low signal not visible, 1 - CAN low signal visible
    - 2: 0 - CAN diff signal not visible, 1 - CAN diff signal visible
    - 3: 0 - CAN CMV signal not visible, 1 - CAN CMV signal visible

If the parameter is set to 0, all available signals for the measurement block are displayed.

## Return Values

- **1**: Success
- **0**: Timeout
- **<0**: Error occurred.

## Example

[Scope Sample Configuration](../../../SampConf/CAN/CANoe/Scope/BitmaskAnalysisCAN.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
