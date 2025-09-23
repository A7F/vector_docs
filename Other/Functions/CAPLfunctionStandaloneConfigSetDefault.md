# StandaloneConfigSetDefault

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword StandaloneConfigSetDefault(CHAR rtcfgFileName[]);
```

## Description

Changes the default configuration file, i.e. the standalone configuration to be loaded when standalone mode is activated or the RT kernel is started after reboot. Thus, it results in a persistent change on the VN8900.

- The given standalone configuration file must have been downloaded to the device before.
- The command can be used while [standalone mode](../../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md) is activated or deactivated.
- Basic behavior corresponds to changing the default standalone configuration file.

## Parameters

- **rtcfgFileName**: Name of the standalone configuration file (without path) to be set as default configuration file.

## Return Values

The function returns an error code with 0 representing successful operation.

## Example

—
