[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStopLogging.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » stopLogging

# stopLogging

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `void stopLogging(); // from 1`
- `void stopLogging(char strLoggingBlockName[]); // from 2`
- `void stopLogging(char strLoggingBlockName[], long postTriggerTime); // from 3`

## Description

- Stops all Logging Blocks immediately bypassing all logging trigger settings.
- Stops a Logging Block with name **strLoggingBlockName** immediately bypassing all logging trigger settings.
- Stops a Logging Block with name **strLoggingBlockName** bypassing all logging trigger settings.
- Functions also sets a post-trigger time to a value of the **postTriggerTime**.

## Parameters

- **strLoggingBlockName**: Name of the Logging Block.
  - **Note**: If you use the function in standalone mode and if you activated logging and Trigger Block in the standalone mode configuration settings you can address the (single) Logging Block available in this case by passing an empty string as parameter.

- **postTriggerTime**: Post-trigger time interval in ms.

## Return Values

—

## Example

```plaintext
startLogging();
// starts all Logging Blocks
stopLogging();
// stops all Logging Blocks
startLogging("Logging 1");
// starts the Logging Block "Logging 1"
stopLogging("Logging 1");
// stops the Logging Block "Logging 1"
startLogging("Logging 1", 2000);
// starts the Logging Block "Logging 1" with pre-trigger time 2000 milliseconds.
stopLogging("Logging 1", 1000);
// stops the Logging Block "Logging 1" with post-trigger time 1000 milliseconds.
```

[StartLogging](CAPLfunctionStartLogging.md)
