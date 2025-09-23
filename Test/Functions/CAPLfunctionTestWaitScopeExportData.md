# testWaitScopeExportData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

`long testWaitScopeExportData (char fullName[]);`

## Description

Export the scope measurement.

## Parameters

- **fullName**: Name of the export file including the absolute path.

## Return Values

- **1**: Success
- **0**: Timeout
- **\< 0**: Error occurred. See **EScopeCAPLFitDataReturnCode** in `<application\>\Reusable\CAPL_Includes\Scope\` [ScopeBitAnalyse.cin](javascript:startDemoLoader('"Reusable\\CAPL_Includes\\Scope"'))

## Example

[Scope Sample Configuration](../../../SampConf/CAN/CANoe/Scope/BitmaskAnalysisCAN.md)
