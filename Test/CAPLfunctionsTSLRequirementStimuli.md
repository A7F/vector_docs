[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/CAPLfunctionsTSLRequirementStimuli.md)

[CAPL Functions](../CAPLfunctions.md) » [Test Service Library](CAPLfunctionsTSLStimulusOverview.md) » Stimulus Generator: Requirements for the Settings of the Trace Window Export

# Requirements for the Settings of the Trace Window Export

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

If the output of the trace shall be used as input for this stimuli, you have to do the following settings in the [Export Settings](../../CANoeCANalyzer/Windows/CANoeCANalyzerWindowsExportConversionAdvanced.md) dialog (Export context menu command of the Trace Window – menu path Advanced Settings|[Settings…]):

## Format

- **Time format**: The identifier for the time column can be 't, 'T' or 'Time'
- **Signal format**: Stimulus supports the 3 possibilities of the trace export
- **Name delimiter**: The limiter has to be '::'
- **Timestamps**: Stimulus supports two formats:
  - Check box active (unit: s)
  - Check box inactive (unit: 10us)

## CSV Settings

- **List limiter**: The limiter has to be Comma ',' or Semi-colon ';'
- **Decimal separator**: The limiter has to be a point, **not** a comma.
- **Decimal places**: No constraints about this.
- **Layout**: The CSV file has to contain one table with a time column if necessary and columns for every signal (first and second option of the window below).
