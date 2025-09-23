[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionTimeNowNS.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » timeNowNS, timeNowInt64

# timeNowNS, timeNowInt64

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
float TimeNowNS();
int64 timeNowInt64();
```

## Description

Supplies the current simulation time.

The simulation time can be correlated with the hardware results of the network interface. The resolution of this time is dependent upon the hardware used (usually a millisecond or better).

Depending on the hardware configuration, the simulation time

- will be the same as the message time calculated by the network interface.

or

- the message times will have a higher accuracy

## Parameters

—

## Return Values

Simulation time in nanoseconds.

## Example

—

[EnvVarTimeNS](CAPLfunctionEnvVarTimeNS.md) • [MessageTimeNS](CAPLfunctionMessageTimeNS.md) • [timeNowFloat](CAPLfunctionTimeNowFloat.md)
