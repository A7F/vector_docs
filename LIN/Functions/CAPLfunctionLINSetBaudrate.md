[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetBaudrate.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetBaudrate

# linSetBaudrate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `void linSetBaudrate(long baudrate);` // form 1
- `Void linSetBaudrate(long minBaudrate, long maxBaudrate);` // form 2

## Description

With this function it is possible to change the baudrate during the measurement. It is also possible to activate automatic baudrate detection in a specified range.

**Note**

- It is recommended setting the baudrate via the database or the hardware configuration dialog. This function is especially useful for test cases (conformance test) which have to run at a number of different baudrates.
- This function can be used also when LIN hardware is not in Master mode.
- During automatic baudrate detection no bus event will be reported until the baudrate has been detected successfully.
- For automatic baudrate detection the min and max baudrate shall only deviate in the range of +-15%.
- With [linSetBaudrateDetectionRange](CAPLfunctionLINSetBaudrateDetectionRange.md) this range can be extended to up to +-30%. `linSetBaudrateDetectionRange` also allows to limit the range.

## Parameters

- **baudrate**: Baudrate to be set [in bit/sec]. Value range: 200 Baud – 30500 Baud
- **minBaudrate**: The lower border of the automatic baudrate detection range. Value range: 200 Baud – maxBaudrate
- **maxBaudrate**: The upper border of the automatic baudrate detection range. Value range: minBaudrate – 30500 Baud

## Return Values

—

## Example

Change baudrate on keyboard event

```plaintext
on key 'w'
{
    linSetBaudrate(9600);  // change baudrate to 9600 bit/sec
}
```

[linMeasHeaderBaudrate](CAPLfunctionLINMeasHeaderBaudrate.md) • [linMeasRespBaudrate](CAPLfunctionLINMeasRespBaudrate.md) • [linSetBaudrateDetectionRange](CAPLfunctionLINSetBaudrateDetectionRange.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
