[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/CAPLfunctionsEventProceduresOverview.md)

[CAPL Functions](../CAPLfunctions.md) » [General](CAPLGeneralStartPage.md) » General Event Procedures

# General Event Procedures

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

CAPL is a procedural language in which the execution of program blocks is controlled by events. These program blocks are referred to as event procedures. Within an event procedure there may be reactions to the following events:

- **Receipt of any message**
  - [on *](EventProcedures/CAPLfunctionOn.md)

- **System variable change**
  - [on sysVar](EventProcedures/CAPLfunctionOnSysVar.md)
  - [on sysVar_change](EventProcedures/CAPLfunctionOnSysVar.md)

- **Notification of system variable updates without value change**
  - [on sysVar_update](EventProcedures/CAPLfunctionOnSysVar.md)

- **Press of a key**
  - [on key](EventProcedures/CAPLfunctionOnKey.md)

- **Elapse of a timer**
  - [on timer](EventProcedures/CAPLfunctionOnTimer.md)

- **State of a replay block has changed**
  - [on replaySourceStatusChanged](EventProcedures/CAPLfunctionOnReplaySourceStatusChanged.md)

- **State of a offline source has changed**
  - [on offlineSourceStatusChanged](EventProcedures/CAPLfunctionOnOfflineSourceStatusChanged.md)

- **Response to Signal Changes**
  - [Response to Signal Changes](../../Shared/CAPL/SignalOrientedProgramming/SOPSignalChange.md)

- **Receipt of a signal**
  - on signal_update

- **Signal change**
  - on signal

- **Events of Measurement System**
  - [Events of Measurement System](EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md)

- **Initialization of measurement (before start)**
  - on preStart

- **Program start**
  - on start

- **Measurement stop has been requested**
  - on preStop

- **End of measurement**
  - on stopMeasurement

- **AUTOSAR PDU**
  - [on PDU](EventProcedures/CAPLfunctionOnPDU.md)

- **Test Support**
  - [on testContextCompleted](EventProcedures/CAPLfunctionOntestContextCompleted.md)

The program code that you define in event procedures is executed when the event occurs. For example, you could send a message onto the bus in response to a key press (`on key`), track the occurrence of messages on the bus (`on message`), or else execute cyclically defined actions (`on timer`).

## Example

[Example](EventProcedures/CAPLfunctionsEventproceduresExample.md)

### Note for Using Handlers within CAPL Test Nodes

Note for preStop handler, event handler and time handler:  
If a test is stopped (test module inactive), these handlers will not be executed within the CAPL test node.

**Example:**

In a XML test module a CAPL test node is added.

```plaintext
on preStart
{
    write ("start");
}

on preStop
{
    write ("stop");
    deferStop (5000);
}
```

If the test module is inactive, the `on preStart() write` is displayed, `on preStop` will not be executed.

[Event Procedures: Overview](../../Shared/CAPL/General/EventProceduresOverview.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
