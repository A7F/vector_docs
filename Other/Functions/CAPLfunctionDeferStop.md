[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionDeferStop.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » DeferStop

# DeferStop

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void DeferStop(dword maxDeferTime);
```

## Description

Defers measurement stop.

The function can be called in the [on preStop](../EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) handler or even at an earlier time instance. Measurement is deferred until [CompleteStop](CAPLfunctionCompleteStop.md) is called in the same node or the simulation time has advanced by the amount given in parameter maxDeferTime since the arrival of a stop request (and call of the on preStop handler).

`DeferStop` enables waiting for completion of activities that have to be carried out before measurement stop takes effect, e.g. a reset of an attached ECU.

**Note:**

- If several CAPL nodes or internal components defer a measurement stop, measurement continues until they have all indicated completion of their pre-stop actions (either by explicitly calling `CompleteStop` or implicitly when the **maxDeferTime** timeout has occurred).
- `DeferStop` may not be called after the CAPL node has indicated completion of pre-stop activities (explicitly or implicitly).
- By calling `DeferStop` twice within the same node the interval until the automatic complete timeout occurs can be extended. Reduction of the timeout interval is not supported.
- If `DeferStop` is called before a stop request arrives measurement stop will be deferred even if an on preStop handler is not defined. The timer whose interval is defined in **maxDeferTime** refers to the instance of the stop request arrival.
- `DeferStop` is not supported in test units and test modules.

## Parameters

- **maxDeferTime**: Indicates the time interval in milliseconds after which completion of pre-stop activities is indicated automatically if it has not yet been done explicitly via [CompleteStop](CAPLfunctionCompleteStop.md).

## Return Values

—

## Example

```plaintext
on preStop
{
   message ShutdownReq m;
   output(m);
   DeferStop(1000);
}
on message ShutdownAck
{
   CompleteStop();
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
