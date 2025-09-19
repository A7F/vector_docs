[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/EventProcedures/CAPLfunctionOn.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Event Procedures](../CAPLfunctionsEventProceduresOverview.md) » on *

# on *

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

You can access the on * event procedure in Measurement Setup.

If you add a CAPL program in Measurement Setup, it will initially act as a filter, as only messages/frames called explicitly in the CAPL program will be allowed through.

`on *` enables all messages/frames not executed in the context of a previous procedure to be forwarded in all bus systems.

You can add the event procedure in the [Navigator](../../../Shared/DocumentView.md#Navigator) of the [CAPL Browser](../../../CAPLBrowser/CAPLBrowser.md).

**Example**

All messages except the CAN message with the ID 500 are forwarded.

```plaintext
// blocking CAN ID 500
on message 500 {
}
on * {
  output(this);
}
```

In the event procedure, the keyword [this](CAPLfunctionKeywordThis.md) can only be used for a call in the `output` function and to read out the time stamp.

**Example**

```plaintext
// counting and viewing all frames (after a filter)
on * {
  write("Received frame nr. %d, time %d", ++gFrameCount, this.time);
  output(this);
}
```

[Unconditional (Boxed) Event Procedures](../CAPLfunctionsBoxedEventProceduresOverview.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
