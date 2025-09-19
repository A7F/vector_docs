[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionCloseLogFile.md)

**CAPL Functions** » **General** » **Function Overview** » **closeLogFile**

# closeLogFile

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void closeLogFile(char loggingBlockName[]);
```

## Description

Explicitly closes the logging file of a given Logging Block. If the Logging Block is running, it will be stopped.

**Note**: If the Logging Block is started again without changing the name of the logging file, the old file will be overwritten.

## Parameters

- **loggingBlockName**: Name of the Logging Block.

  **Note**: If you use the function in standalone mode and if you activated Logging and Trigger Block in the [standalone mode configuration settings](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/StandaloneModeLoggingConfiguration.md) you can address the (single) Logging Block available in this case by passing an empty string as parameter.

## Return Values

—

## Example

```plaintext
startLogging("Logging"); // starts the Logging Block "Logging"
...
stopLogging("Logging"); // stops the Logging Block "Logging"
...
startLogging("Logging"); // restarts the Logging Block "Logging", data will be appended
...
closeLogFile("Logging"); // stops the Logging Block "Logging" and closes the logging file
sysExecCmd("copy", "C:\\tmp\\LogFile.blf C:\\backup\\LogFile.blf"); // copies the logging file
startLogging("Logging"); // restarts the Logging Block "Logging", logging file will be overwritten
```

[stopLogging](CAPLfunctionStopLogging.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
