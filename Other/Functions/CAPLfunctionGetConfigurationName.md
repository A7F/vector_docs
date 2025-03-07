[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetConfigurationName.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getConfigurationName

# getConfigurationName

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long getConfigurationName(char buffer[], dword bufferLength);
```

## Description

Returns the filename of the currently loaded configuration. It includes neither the filename extension nor any path information, for example **CANSystemDemo**.

**Note**  
Difference between StandaloneGetCurrentConfig and getConfigurationName

There are two kinds of configurations in standalone mode:

- the standalone configuration (with filename extension RTCFG)
- the normal configuration (with filename extension CFG) associated to the standalone configuration.

These two filenames may well differ (even though normally they are the same except for the filename extension).

[StandaloneGetCurrentConfig](CAPLfunctionStandaloneGetCurrentConfig.md) returns the standalone configuration filename, whereas **getConfigurationName** returns the normal configuration filename.

## Parameters

- **buffer**: Space for the returned name.
- **bufferLength**: Length of the buffer.

## Return Values

- **-1**: Buffer too small.
- **>= 0**: Operation successful. The return value specifies the length of the configuration name.

## Example

```plaintext
on start
{
  char cfgName[260];
  dword ret;
  ret = getConfigurationName(cfgName,elcount(cfgName));
  write("getConfigurationName returns %d %s", ret, cfgName);
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)