[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStandaloneConfigOpen.md)

**CAPL Functions** » **General** » **Function Overview** » **StandaloneConfigOpen**

# StandaloneConfigOpen

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword StandaloneConfigOpen(CHAR rtcfgFileName[], dword stopCurrentMeasurement, dword startNewMeasurement, dword returnToActiveConfig)
```

## Description

Opens the **RTCFG** file with the given name as standalone configuration.

- The given standalone configuration file must have been downloaded to the device before.
- The command is only allowed while [standalone mode](../../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md) is activated.
- If standalone measurement is currently running the command is deferred until end of measurement (unless overwritten by another subsequent open command).
- If standalone measurement is not running but standalone mode is activated the file is loaded but measurement is not started automatically.
- Basic behavior corresponds to changing the default standalone configuration file.

## Parameters

- **rtcfgFileName**: Name of the standalone configuration file (without path) to be set as default file.
- **stopCurrentMeasurement**: If this parameter is 1 measurement is stopped immediately (but still waiting for deferred stop clients). If the parameter value is 0 the request to load another configuration is queued until end of measurement.
- **startNewMeasurement**: If this parameter is set to 1 measurement will start immediately after the new configuration has been loaded.
- **returnToActiveConfig**: If this parameter is set to 1 the default configuration (usually a sort of "master configuration") will be loaded automatically after measurement based on the new configuration will have been stopped.

## Return Values

The function returns an error code with 0 representing successful operation.

## Example

```c
// "Config1.RTCFG" (master config.) contains following CAPL code:

on key F2
{
   StandaloneConfigOpen("Config2.RTCFG", 1, 1, 1);
}
on key F3
{
   StandaloneConfigOpen("Config3.RTCFG", 1, 0, 1);
}
```

[StandaloneConfigSetDefault](CAPLfunctionStandaloneConfigSetDefault.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
