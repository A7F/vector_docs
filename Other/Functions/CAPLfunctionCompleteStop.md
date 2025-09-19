[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionCompleteStop.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » CompleteStop

# CompleteStop

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void CompleteStop ();
```

## Description

Indicates completion of pre-stop actions carried out in a certain node after a measurement stop has been deferred by [DeferStop](CAPLfunctionDeferStop.md).

**Note**

- If several CAPL nodes or internal components defer a measurement stop, measurement continues until they have all indicated completion of their pre-stop actions (either by explicitly calling `CompleteStop` or implicitly when the timeout whose interval has been defined in the [DeferStop](CAPLfunctionDeferStop.md) call has passed).
- `CompleteStop` may not be called before a stop request has arrived (i.e. before the [on preStop](../EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) handler is called).

## Parameters

—

## Return Values

—

## Example

```plaintext
on preStop
{
   message ShutdownReq m;

   output(m);
   DeferStop(1000);  // measurement is stopped if ACK has not
                     // yet been received after one second
}
on message ShutdownAck
{
   CompleteStop();
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
