# testWaitScopeGetConfigurationInformation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long testWaitScopeGetConfigurationInformation (char deviceNames[][], dword deviceCount, char configurationNames[][], dword configurationCount);
```

## Description

Returns the available oscilloscopes and possible configurations. The returned device names and function can be used with the function [testWaitScopeSetConfiguration](CAPLfunctiontestWaitScopeSetConfiguration.md).

## Parameters

- **deviceNames**: The names of the scope device.
- **deviceCount**:
  - [in] The number of scope devices requested
  - [out] The number of available scope devices
- **configurationNames**: The configuration names of all available configurations.
- **configurationCount**:
  - [in] The number of requested configurations
  - [out] The number of available configurations

## Return Values

- **1**: Successful
- **0**: Timeout
- **-24**: If the array for the string is too small.
- **-25**: If the number of devices is not equals to the requested devices.
- **-26**: If the number of configurations is not equals to the requested configurations.
- **-27**: If the array for the strings is \> 260.

## Example

```c
includes
{
  #include "scope\ScopeBitAnalyse.cin"
}
variables
{
}
testcase GetScopeConfiguration()
{
  char deviceNames[1][50];
  char configNames[2][50];

  GetConfigInfo(deviceNames, 1, 50, configNames, 2, 50
}
testfunction GetConfigInfo(char currDevNames[][], dword devCount, dword devStringLength, char currConfigNames[][], dword configCount, dword confStringLength)
{
  long res;
  int i,j;
  int wantedDeviceCount;
  int wantedConfigCount;
  int minConfCount;
  int minDevCount;

  wantedDeviceCount=devCount;
  wantedConfigCount=configCount;

  testStep("testWaitScopeGetConfigurationInformation", "Input deivceNames [Array-Length: 1d=%d 2d=%d] count %d configNames [Array-Length: 1d=%d 2d=%d] count =%d", devCount, devStringLength, devCount, configCount, confStringLength, configCount);
  res = testWaitScopeGetConfigurationInformation(currDevNames, devCount, currConfigNames, configCount); 

  if(res == eCAPLScopeResult_Success)
  {
    testStepPass("testWaitScopeGetConfigurationInformation", "Output deivceNames devices written %d; config names written %d", devCount, configCount);
  }
  else
  {
    testStepWarning("testWaitScopeGetConfigurationInformation", "InputData doesn't fit request (Error Code %d) deviceCountExpected =%d deviceCountActual =%d configCountExpected =%d configCountActual =%d", res, wantedDeviceCount, devCount, wantedConfigCount, configCount);
  }

  if(resultExpected != eCAPLScopeResult_eScopeConfigurationToLongArray)
  {
    minDevCount = _min(wantedDeviceCount, devCount);
    for(i = 0; i < minDevCount; ++i)
    {
      testStep("DeviceConfigName", "DeviceName =%s", currDevNames[i]);
    }

    minConfCount= _min(wantedConfigCount, configCount);

    for(j = 0; j < minConfCount; ++j)
    {
      testStep("ConfigurationName", "ConfigName =%s", currConfigNames[j]);
    }
  }
}
```

See also: [testWaitScopeSetConfiguration](CAPLfunctiontestWaitScopeSetConfiguration.md)
