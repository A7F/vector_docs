[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/EventProcedures/CAPLfunctionAFDXOnA664Message.md)

[CAPL Functions](../../CAPLfunctions.md) » [AFDX](../CAPLfunctionsAFDXOverview.md) » on a664Message

# on a664Message

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
CAPL programs are by default not transparent to bus events. This means that a CAPL node in the evaluation branch of the measurement setup will block the data flow to its right side. You must explicitly code the forwarding of messages in CAPL nodes in the evaluation branch. In order to re-use this code snippet in the Simulation Setup of your CANoe DE product you have to add conditional compilation. Otherwise a recursion will occur.

Forward AFDX message event:

```plaintext
on a664Message * {
  #if MEASUREMENT_SETUP
  output(this);
  #endif
}
```

Detect real message in CAPL:

```plaintext
on a664Message * {
  if (this.dir == RX) {
    if (!this.SIMULATED) {
      write("AFDX message received from real system");
    }
    else {
      write("AFDX message received from simulated component");
    }
  }
}
```

## Function Syntax

`on a664Message <message identification>`

## Description

The event procedure **on a664Message** is called on every AFDX message if the following conditions are fulfilled:

- The message id corresponds to the given id (asterisk means "any message").
- The message carries a UDP message.

Additional information related to this event is available via the [selectors](../CAPLfunctionsAFDXSelectors.md). The keyword [this](../../Other/EventProcedures/CAPLfunctionKeywordThis.md) is available within an **on a664Message** procedure, to access the data of the AFDX event that has just been received.

## Selectors

[Selectors for AFDX messages](../CAPLfunctionsAFDXSelectors.md)

## Example

Calling conventions for the **on a664Message** handler

- `on a664Message 0x30e40021`: event with Id 0x30e40021 (hexadecimal)
- `on a664Message 123423`: event with Id 123423 (decimal)
- `on a664Message MSG_INT3`: event with Id from assigned database
- `on a664Message *`: event with any Id
- `on a664Message MsgChannel1.*`: event with any Id on channel 1
- `on a664Message MsgChannel1.0x30e40021`: event with Id 0x30e40021 (hexadecimal) on channel 1
- `on a664Message MsgChannel1.123423`: event with Id 123423 (decimal) on channel 1
- `on a664Message MsgChannel1.MSG_INT3`: event with Id from assigned database on channel 1

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)