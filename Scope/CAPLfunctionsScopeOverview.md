# Scope CAPL Functions

[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Scope/CAPLfunctionsScopeOverview.md)

[CAPL Functions](../CAPLfunctions.md) » Scope CAPL Functions

**Valid for**: CANoe DE • CANoe:lite DE

## ON THIS PAGE:

- [Event Procedures](#EventProcedures)
- [Eye Diagram](#EyeDiagram)
- [General Functions](#General)

**Test Feature Set**

- [Acquisition Control Classes and Functions](#AcquisitionControl)
- [Configuration](#Configuration)
- [Duty Cycle Measurement Classes](#DutyCycleMeas)
- [Edge/Transition Time Measurement Functions](#EdgeTransitionTimeMeas)
- [Export Functions](#Export)
- [Fit Functions](#Fit)
- [Serial Bit Analysis Functions and Classes](#SerialBitAnalysis)

## Event Procedures 

### Functions

- [on ScopeEvent](EventProcedures/CAPLfunctionOnScopeEvent.md): Occurrence of a Scope event.

## Eye Diagram 

### Classes

- [ScopeSinglePolygonBitMask](Classes/CAPLFunctionScopeSinglePolygonBitMask.md): Defines the bitmask for the eye diagram.
- [ScopeSerialBitAnalysisViolationData](Classes/CAPLfunctionScopeSerialBitAnalysisViolationData.md): In case of a bitmask error, holds the information for this error.

### Functions

- [testWaitForScopeShowEyeDiagram](../Test/Functions/CAPLfunctionTestWaitForScopeShowEyeDiagram.md): Create an eye diagram for a message or node.
- [testWaitScopeGetEyeDiagramAnalysis](../Test/Functions/CAPLfunctionTestWaitScopeGetEyeDiagramAnalysis.md): Request analysis data for a violation found with the eye diagram.
- [testWaitScopePerformEyeDiagramAnalysis](../Test/Functions/CAPLFunctionTestWaitScopePerformEyeDiagramAnalysis.md): Check bits against a defined bitmask.

## General Function 

### Functions

- [scopeActivateTrigger](Functions/CAPLfunctionScopeActivateTrigger.md): Performs Activate Trigger action for Scope Window.
- [scopeConnect](Functions/CAPLfunctionScopeConnect.md): Performs Connect Scope action for Scope Window.
- [scopeDeactivateTrigger](Functions/CAPLfunctionScopeDeactivateTrigger.md): Performs Deactivate Trigger action for Scope Window.
- [scopeDisconnect](Functions/CAPLfunctionScopeDisconnect.md): Performs Disconnect Scope action for Scope Window.
- [scopeTriggerNow](Functions/CAPLfunctionScopeTriggerNow.md): Performs Trigger Now action for Scope Window.

## Test Feature Set for Scope

### Acquisition Control Classes and Functions 

#### Classes

- [ScopeEvent](Classes/CAPLfunctionsScopeEvent.md): Detailed description of occurred scope event.

### Configuration 

#### Functions

- [testWaitScopeSetConfiguration](../Test/Functions/CAPLfunctiontestWaitScopeSetConfiguration.md): Set the configuration for the scope device.
- [testWaitScopeGetConfigurationInformation](../Test/Functions/CAPLfunctionTestWaitScopeGetConfigurationInformation.md): Get the scope devices and configuration names.

### Duty Cycle Measurement Classes 

#### Classes

- [ScopeDutyCycleDefinition](Classes/CAPLfunctionScopeDutyCycleDefinition.md): Defines the thresholds for duty cycle measurement.
- [ScopeBitDataDutyCycle](Classes/CAPLfunctionScopeBitDataDutyCycle.md): Request duty cycle measurement data.
- [ScopeSerialBitAnalysisViolationData](Classes/CAPLfunctionScopeSerialBitAnalysisViolationData.md): Request duty cycle measurement violation data.

### Edge/Transition Time Measurement Functions 

#### Classes

- [ScopeEdgeAnalyseResult](Classes/CAPLfunctionScopeEdgeAnalysisResult.md): Contains information for slew rate, transition time, etc.

#### Functions

- [testGetWaitScopeSignalTransitionTime](../Test/Functions/CAPLfunctionTestGetWaitScopeSignalTransitionTime.md): Measures transition time of edges.
- [testWaitForScopeShowEdges](../Test/Functions/CAPLfunctionTestWaitForScopeShowEdges.md): Shows frame cutout in scope's Diagram view.
- [testWaitScopePerformEdgeAnalysis](../Test/Functions/CAPLfunctionTestWaitScopePerformEdgeAnalysis.md): Measures edge parameters.
- [testWaitScopePerformSignalTransitionTime](../Test/Functions/CAPLfunctionTestWaitScopePerformSignalTransitionTime.md): Measures transition time on bit level.

### Export Functions 

#### Functions

- [testWaitScopeExportData](../Test/Functions/CAPLfunctionTestWaitScopeExportData.md): Export the scope measurement.

### Fit Functions 

#### Fit Functions

- [testWaitForScopeFitData](../Test/Functions/CAPLfunctionTestWaitForScopeFitData.md): Shows frame cutout in scope's Diagram view (CAN).
- [testWaitForScopeFitDataFr](../Test/Functions/CAPLfunctionTestWaitForScopeFitDataFr.md): Shows frame cutout in scope's Diagram view (FlexRay).

### Serial Bit Analysis Functions and Classes 

#### Classes

- [ScopeFieldLengthData](Classes/CAPLfunctionScopeFieldLengthData.md): Contains information like bit time, start time.
- [ScopeAnalyseRange](Classes/CAPLfunctionScopeAnalyseRange.md): Defines analyze range for bit analysis.

#### Functions

- [testWaitForScopeAnalyseBitSegments](../Test/Functions/CAPLfunctionTestWaitForScopeAnalyseBitSegments.md): Starts analysis for defined bit segments.
- [testWaitScopeGetFieldLengthData](../Test/Functions/CAPLfunctionTestWaitScopeGetFieldLengthData.md): Gets bit time of one bit.
- [testWaitForScopePerformFieldLengthMeasurement](../Test/Functions/CAPLfunctionTestWaitForScopePerformFieldLengthMeasurement.md): Measures time of a field range.
- [testWaitScopeAnalyseSignal](../Test/Functions/CAPLfunctionTestWaitScopeAnalyseSignal.md): Checks bits against bitmask.
- [testWaitScopeGetAnalysedBitSegments](../Test/Functions/CAPLfunctionTestWaitScopeGetAnalysedBitSegments.md): Request analysis data for a single bit.
- [testWaitScopeGetBitInfo](../Test/Functions/CAPLfunctionTestWaitScopeGetBitInfo.md): Calculates average values of voltages for a bit range.
- [testWaitScopeGetMaskViolation](../Test/Functions/CAPLfunctionTestWaitScopeGetMaskViolation.md): Retrieve data of bitmask violations.
- [testWaitScopeGetMessageBits](../Test/Functions/CAPLfunctionTestWaitScopeGetMessageBits.md): Gets specific bit values from a message.
- [testWaitScopeGetSerialBitAnalysisData](../Test/Functions/CAPLfunctionTestWaitScopeGetSerialBitAnalysisData.md): Get data for serial bit analysis.
- [testWaitScopeGetSerialBitAnalyseViolationData](../Test/Functions/CAPLfunctionTestWaitScopeGetSerialBitAnalyseViolationData.md): Request violations found in serial bit analysis.
- [testWaitScopePerformSerialBitAnalysis](../Test/Functions/CAPLfunctionTestWaitScopePerformSerialBitAnalysis.md): Checks bits against bitmask.
- [testWaitScopeShowMask](../Test/Functions/CAPLfunctionTestWaitScopeShowMask.md): Shows frame cutout with bitmask in scope's Diagram view.

[Classes in CAPL](../ObjectOrientedProg/CAPLfunctionsOOPClassesObjects.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
