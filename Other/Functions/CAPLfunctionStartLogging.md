[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStartLogging.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » startLogging

# startLogging

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `void startLogging(); // from 1`
- `void startLogging(char strLoggingBlockName[]); // from 2`
- `void startLogging(char strLoggingBlockName[], long preTriggerTime); // from 3`

## Description

- Starts all Logging Blocks immediately bypassing all logging trigger settings.
- Starts a Logging Block with name **strLoggingBlockName** immediately bypassing all logging trigger settings.
- Function also sets a pre-trigger time to a value of the **preTriggerTime**.

## Parameters

- **strLoggingBlockName**: Name of the Logging Block.

  **Note**: If you use the function in standalone mode and if you activated logging and Trigger Block in the standalone mode configuration settings you can address the (single) Logging Block available in this case by passing an empty string as parameter.

- **preTriggerTime**: Pre-trigger time interval in ms.

  **Note**: While using the **preTriggerTime** please pay attention to the fact, that the buffer size in the trigger configuration dialog of the Logging Block is set accordingly, so that all events of the given time interval can be logged.

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

[StopLogging](CAPLfunctionStopLogging.md)
