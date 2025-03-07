[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/EventProcedures/CAPLfunctionOnLINCsError.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » on linCsError

# on linCsError

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Description

The event procedure `on linCsError` is called when a frame was transmitted without a failure, but with an incorrect checksum.

The keyword `this` and the selectors can be used to access the data of the event that has just been received.

## Selectors

- [linCsError](../Selectors/CAPLfunctionLINCSError.md)

## Example

Simulate checksum error and check how it is handled.

```plaintext
on key 'c'
{
    int index;
    byte checksum;
    linFrame MotorControl frmMotorControl;
    // set data byte values and calculate resulting checksum
    for (index=0; index < frmMotorControl.DLC; ++index)
    {
        frmMotorControl.byte(index) = 0xFF;
    }
    // Set permanent CS error for the current frame
    linSetChecksumError(frmMotorControl.id, 1);
    // update response data
    frmMotorControl.RTR=0;
    output(frmMotorControl);  
    // apply frame's header on the bus
    frmMotorControl.RTR=1;
    output(frmMotorControl);
}
...
on linCsError
{
    int index;
    linFrame MotorControl frmMotorControl;
    // compare correct checksum and the received one
    if (this.ID == frmMotorControl.ID)
    {
        // set data byte values and calculate correct checksum
        for (index=0; index < frmMotorControl.DLC; ++index)
        {
            frmMotorControl.byte(index) = this.byte(index);
        }
        WriteLineEx(0,0,"received checksum=%d", getChecksum(this));
        WriteLineEx(0,0,"correct checksum=%d", getChecksum(frmMotorControl));
    }
}
```

[LINSetChecksumError](../Functions/CAPLfunctionLINSetChecksumError.md) • LINGetChecksum

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)