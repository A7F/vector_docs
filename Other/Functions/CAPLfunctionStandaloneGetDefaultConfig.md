[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStandaloneGetDefaultConfig.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » StandaloneGetDefaultConfig

# StandaloneGetDefaultConfig

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword StandaloneGetDefaultConfig(char cfgNameBuffer[], dword cfgNameBufferLength);
```

## Description

Gets the name of the default configuration in standalone mode. This is the standalone configuration, which gets loaded when [standalone mode](../../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md) is activated or the RT kernel is started after reboot.

The command can be used while standalone mode is running. It is also useful to determine whether standalone mode is running or not.

A returned configuration name consists of the filename and the extension, for example **CANSystemDemo.rtcfg**.

## Parameters

- **cfgNameBuffer**: Space for the returned name.
- **cfgNameBufferLength**: Length of the buffer.

## Return Values

- **0**: Successful operation
- **1**: Buffer too small
- **2**: Not in standalone mode

## Example

```plaintext
on start
{
  char cfgName[200];
  DWORD cfgRet;
  cfgName[0]=0;
  cfgRet=StandaloneGetDefaultConfig(cfgName,elcount(cfgName));
  write("StandaloneGetDefaultConfig returns %d %s",cfgRet,cfgName);
}
```

[StandaloneGetCurrentConfig](CAPLfunctionStandaloneGetCurrentConfig.md) • [StandaloneConfigSetDefault](CAPLfunctionStandaloneConfigSetDefault.md) • [StandaloneConfigOpen](CAPLfunctionStandaloneConfigOpen.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)