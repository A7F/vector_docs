[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStandaloneGetCurrentConfig.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » StandaloneGetCurrentConfig

# StandaloneGetCurrentConfig

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
dword StandaloneGetCurrentConfig(char cfgNameBuffer[], dword cfgNameBufferLength);
```

## Description

Returns the filename of the currently loaded configuration in standalone mode. It includes the filename extension, but no path information, for example **CANSystemDemo.rtcfg**.

The function can be used in [standalone mode](../../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md). It is also useful to determine whether standalone mode is active or not.

**Note**  
Difference between StandaloneGetCurrentConfig and getConfigurationName

There are two kinds of configurations in standalone mode:

- the standalone configuration (with filename extension RTCFG)
- the normal configuration (with filename extension CFG) associated to the standalone configuration.

These two filenames may well differ (even though normally they are the same except for the filename extension).

**StandaloneGetCurrentConfig** returns the standalone configuration filename, whereas [getConfigurationName](CAPLfunctionGetConfigurationName.md) returns the normal configuration filename.

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
  cfgRet=StandaloneGetCurrentConfig(cfgName,elcount(cfgName));
  write("StandaloneGetCurrentConfig returns %d %s",cfgRet,cfgName);
}
```

[StandaloneGetDefaultConfig](CAPLfunctionStandaloneGetDefaultConfig.md) • [StandaloneConfigSetDefault](CAPLfunctionStandaloneConfigSetDefault.md) • [StandaloneConfigOpen](CAPLfunctionStandaloneConfigOpen.md)

© Vector Informatik GmbH  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)