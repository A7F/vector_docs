[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/EventProcedures/CAPLfunctionOnLINFrame.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » on linFrame

# on linFrame

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Description

The event procedure `on linFrame` is called on the receipt of a valid LIN frame.

The keyword `this` and the selectors (see LIN: [linFrame selectors](../Selectors/CAPLfunctionLINMessage.md)) can be used to access the data of the frame that has just been received.

CAPL nodes are by default not transparent to LIN frames. This means that a CAPL node in the evaluation branch of the Measurement Setup will block the data flow to its right side. To propagate the received frame to a next node in a chain a call to [output(this)](../Functions/CAPLfunctionLINOutput.md) can be used. However, please note that such a call from a CANoe's Simulation Setup node may lead to a recursion.

**Note**

If for example a CAPL program contains the event procedures `on linFrame 12` and `on linFrame *`, the procedure `on linFrame 12` will be called up, when a frame with the identifier 12 is received. For all other frames the procedure `on linFrame *` will be called up.

## Selectors

- [linFrame](../Selectors/CAPLfunctionLINMessage.md)

## Example

Display in Write Window the transmission time for a frame from the database

```plaintext
on linFrame MotorControl
{
    writeLineEx(1, 1, "Entire frame transmission time: %d bit times", this.LIN_Fulltime);
}
```

Display in Write Window the header transmission time for a frame ID=0x33

```plaintext
on linFrame 0x33
{
    writeLineEx(1, 1, "Frame header transmission time: %d bit times", this.LIN_HeaderTime);
}
```

Propagate all frames to a next chain node

```plaintext
// Warning: This code causes recursion when called from Simulation Setup node
on linFrame *
{
    this.RTR=1;
    output(this);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
