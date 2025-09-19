[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Event Procedures](../CAPLfunctionsEventProceduresOverview.md) » Events of the Measurement System

# Events of the Measurement System

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

These event procedures are called before the start of measurement, at the start, and when the measurement is ended. For example, you can initialize variables here, output a start report to the Write Window with the [write](../Functions/CAPLfunctionWrite.md) function, start [Timer](CAPLfunctionOnTimer.md) or output statistics after the end of measurement.

The `on preStart` procedure is only used to initialize variables, to display messages in the Write Window and to read in data from files. At the moment the `on preStart` procedure is executed, not all possibilities of the system (CANoe DE product) are available. It is not possible for example to send messages on the bus with the [output](../../CAN/Functions/CAPLfunctionOutput.md) function.

The `on preStop` handler is called after a measurement stop has been requested. The `on preStop` function can be used to execute some final actions that must be done before the measurement stop actually takes effect. Note that some actions, such as setting environments, would have no effect if they were only initiated in `on StopMeasurement`. If more complex pre-stop actions like sending a shutdown message to an attached ECU and waiting for an acknowledgment message are required, a [DeferStop](../Functions/CAPLfunctionDeferStop.md) call within the `on preStop` function might be useful to further defer the measurement stop. If [DeferStop](../Functions/CAPLfunctionDeferStop.md) is not called in the CAPL node, all pre-stop activities are assumed to be completed after the `on preStop` handler is finished, i.e. measurement immediately stops unless there are other nodes that are deferring a measurement stop.

**Note**

At the measurement start it may be necessary, in the network node models, to execute the same actions that otherwise would be performed during the measurement when environment variables change. In particular, it may be necessary to initialize environment variables, to start timers activated in response to changes of environment variables, or to send messages on the bus with the start values of environment variables.

**Note for Test Feature Set Users**

Within test units and test modules, it is not sensible to initialize variables within the `on prestart` handler, because all variables will be cleared on each start of the test unit/test module. Use the test scenario itself to initialize variables. Refer to [Introduction to Testing with CANoe](../../../CANoeCANalyzer/Test/TestFeatureSet/TFSIntroduction.md) for more details.

**Example**

**on preStart procedure**

```plaintext
on preStart
{
   write("Measurement started!");
   msg_Count = 0;
}
```

**on start procedure**

```plaintext
on start
{
   write("start Node A");
   setTimer(cycTimer,20);
}
```

**on preStop procedure**

```plaintext
on preStop
{
   message ShutdownReq m;

   output(m);
   DeferStop(1000);
}
```

**on stopMeasurement procedure**

```plaintext
on stopMeasurement
{
   write("Message 0x%x received: %d", msg.id, msg_Count);
}
```

**Note for Using Handler within CAPL Test Nodes**

Note for preStop handler, event handler and time handler: If a test is stopped (test module inactive), these handlers will not be executed within the CAPL test node.

**Example:**

In a XML test module a CAPL test node is added.

```plaintext
on preStart
{
   write ("start");
}
```

```plaintext
on preStop
{
   write ("stop");
   deferStop (5000);
}
```

If the test module is inactive, the `on preStart() write` is displayed, `on preStop` will not be executed.

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
