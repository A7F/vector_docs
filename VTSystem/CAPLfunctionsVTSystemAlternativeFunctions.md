[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/CAPLfunctionsVTSystemAlternativeFunctions.md)

[CAPL Functions](../CAPLfunctions.md) » [VT System](CAPLfunctionsVTSystemOverview.md) » Differences between Functions and Methods

# Differences between Functions and Methods

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

CAPL offers two different notations for calling the functions of the VT System. On the one hand they can be called as **methods** on the namespaces of the modules and channels. On the other hand it is also possible to call them as **global functions**. In this case the namespace of the module resp. channel is passed as a string argument. Both notations will be illustrated with two simple examples in the following.

## VT System Methods

This is the notation recommended in most cases. Its advantage is that the CAPL compiler can verify the namespace of the module resp. channel already at compile time.

**Example**

In this example one channel of a VT1004 module is configured for PWM measurement.

```plaintext
ConfigurePWMMeasurement()
{
   // Configure channel for PWM measurement
   sysvar::VTS::RPMSensor.SetPWMMeasurementDuration(0.1); // 100ms
   sysvar::VTS::RPMSensor.SetPWMThreshold(2.5);           // 2.5V
}
```

## VT System Functions

For every method of the VT System there is a function with the same name. To allow differentiating these two each function starts with the prefix **vts**. The main difference to the methods is that the functions take the name of their target namespace as a string argument. Because of that the function notation is well suited for creating generic test functions.

**Example**

In this example the code for PWM initialization is implemented in a generic way so that it can be reused for different channels.

```plaintext
testcase TestSensors ()
{
   // Initialize PWM measurement on channels
   ConfigurePWMMeasurement("VTS::RPMSensor");
   ConfigurePWMMeasurement("VTS::TempSensor");
   ...
}

ConfigurePWMMeasurement(char channelName[])
{
   // Configure channel for PWM measurement
   vtsSetPWMMeasurementDuration(channelName, 0.1); // 100ms
   vtsSetPWMThreshold(channelName, 2.5);           // 2.5V
}
```

[VT System CAPL Functions](CAPLfunctionsVTSystemOverview.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
