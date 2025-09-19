[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionTimeNow.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » timeNow

# timeNow

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword timeNow();
```

## Description

Supplies the current simulation time (maximum time: .2^32 * 10 microseconds = 11 hours, 55 minutes, 49 seconds, 672 milliseconds, 96 microseconds)

The simulation time can be correlated with the hardware results of the network interface. The resolution of this time is dependent upon the hardware used (usually a millisecond or better).

Depending on the hardware configuration, the simulation time

- will be the same as the message time calculated by the network interface.

or

- the message times will have a higher accuracy

## Parameters

—

## Return Values

Simulation time in 10 microseconds.

## Example

```c
...
float x;
x = timeNow()/100000.0; //current time in seconds
...
```

[timeDiff](CAPLfunctionTimeDiff.md) • [timeNowFloat](CAPLfunctionTimeNowFloat.md) • [timeNowNS](CAPLfunctionTimeNowNS.md) • [timeNowInt64](CAPLfunctionTimeNowNS.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
