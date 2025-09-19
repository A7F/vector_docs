[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/EventProcedures/CAPLfunctionOnServiceSignalUpdate.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » on serviceSignal_update

# on serviceSignal_update

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

`on serviceSignal_update <signal>;`

## Description

This function is called when the associated SOME/IP message has been received. It is immaterial whether or not the signal value was changed. Within the callback function you have direct access to the signal value via keyword [this](../../Other/EventProcedures/CAPLfunctionKeywordThis.md):

- **Key Word:** `this`
  - **Description:** Access to the physical value of the [Service Signal](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md)
  - **Data Type:** FLOAT

- **Key Word:** `this.raw`
  - **Description:** Access to the raw value of the Service Signal
  - **Data Type:** FLOAT

- **Key Word:** `this.raw64`
  - **Description:** Access to the raw value of the Service Signal
  - **Data Type:** QWORD

## Parameters

—

## Selectors

—

## Example

```plaintext
// the following function is called if the Service Signal value was updated
on serviceSignal_update DemoDatabase::PACKAGE1::PACKAGE2::Service1::1::2::Event1::Param1_CommonDataType
{
  int   rwaValue;
  float physValue;

  rwaValue  = this.raw;
  physValue = this;

  write("Service Signal update: Service Signal 'Param1_CommonDataType' received (physical value: %f, raw value: %d)", physValue, rwaValue);
}
```

**Note**

The parameter `Param1_CommonDataType` is contained in `Event1` of service `Service1` (Major Version 1, Instance ID 2). The service interface is defined in package `PACKAGE1::PACKAGE2` of database `DemoDatabase`.

[See Also](javascript:void(0);)
