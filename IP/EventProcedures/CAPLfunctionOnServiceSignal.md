[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/EventProcedures/CAPLfunctionOnServiceSignal.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **on serviceSignal**

# on serviceSignal

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

`on serviceSignal <signal>;`

## Description

This function is called when the signal value is changed and the associated SOME/IP message has been received. Within the callback function, you have direct access to the signal value via keyword [this](../../Other/EventProcedures/CAPLfunctionKeywordThis.md):

- **Key Word**: `this`
  - **Description**: Access to the physical value of the [Service Signal](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md)
  - **Data Type**: FLOAT

- **Key Word**: `this.raw`
  - **Description**: Access to the raw value of the Service Signal
  - **Data Type**: FLOAT

- **Key Word**: `this.raw64`
  - **Description**: Access to the raw value of the Service Signal
  - **Data Type**: QWORD

## Parameters

—

## Selectors

—

## Example

```plaintext
// the following function is called if the Service Signal value was changed
on serviceSignal DemoDatabase::PACKAGE1::PACKAGE2::Service1::1::2::Event1::Param1_CommonDataType
{
  int   rwaValue;
  float physValue;

  rwaValue  = this.raw;
  physValue = this;

  write("Service Signal changed: Service Signal 'Param1_CommonDataType' received (physical value: %f, raw value: %d)", physValue, rwaValue);
}
```

[See Also](javascript:void(0);)
