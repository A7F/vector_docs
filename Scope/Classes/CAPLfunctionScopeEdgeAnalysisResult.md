[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Scope/Classes/CAPLfunctionScopeEdgeAnalysisResult.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../CAPLfunctionsScopeOverview.md) » Class: ScopeEdgeAnalysisResult

# Class: ScopeEdgeAnalysisResult

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

This structure holds the minimal, maximal, standard deviation and average values which are measured by calling the function [testWaitScopePerformEdgeAnalysis](../../Test/Functions/CAPLfunctionTestWaitScopePerformEdgeAnalysis.md).

The figure shows the measured values for a recessive to dominant change for the differential signal.

**Note**  
To measure the delay and compensation time a secant is used. The secant points are by 10% and 90% of the voltage swing between the sample points of the recessive and dominant voltage. The secant is also used to measure the transition time (TT) and the slew rate (SR).

## Methods

—

## Attributes

- **Keyword**: ParameterUnit
  - **Description**: The unit the parameter is measured
  - **Type**: char[32]
  - **Access Limitations**: Read-only

- **Keyword**: ParameterUnit
  - **Description**: The type of the parameter. Possible values are:
    - 0 – TransitionTime (TT)
    - 1 – Slew Rate (SR)
    - 2 -  Delay Time (TD)
    - 3 – Half Value Time (TH)
    - 4 – Compensation Time (TC)
    - 5 – Response Time(TR)
    - 6 – Settling Time (TS)
  - **Type**: long
  - **Access Limitations**: Read/Write

- **Keyword**: Min
  - **Description**: Minimal value of the parameter
  - **Type**: double
  - **Access Limitations**: Read-only

- **Keyword**: Max
  - **Description**: Maximal value of the parameter
  - **Type**: double
  - **Access Limitations**: Read-only

- **Keyword**: Avg
  - **Description**: The average value of the parameter
  - **Type**: double
  - **Access Limitations**: Read-only

- **Keyword**: StdDeviation
  - **Description**: The standard deviation of the parameter
  - **Type**: double
  - **Access Limitations**: Read-only

- **Keyword**: ScopeSamplePeriod
  - **Description**: The sample period of the used scope device.
  - **Type**: double
  - **Access Limitations**: Read-only

- **Keyword**: CountAnalyzedEdges
  - **Description**: The count of measured edges
  - **Type**: double
  - **Access Limitations**: Read-only

- **Keyword**: CountAnalyzedFrames
  - **Description**: The count of measured frames
  - **Type**: double
  - **Access Limitations**: Read-only

[testWaitScopePerformEdgeAnalysis](../../Test/Functions/CAPLfunctionTestWaitScopePerformEdgeAnalysis.md)
