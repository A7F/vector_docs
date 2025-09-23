# on testContextCompleted

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/EventProcedures/CAPLfunctionOntestContextCompleted.md)

**CAPL Functions** » **General** » **Event Procedures** » Test Support » **on testContextCompleted**

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

With the **on testContextCompleted** procedure, the code coverage use case is supported. This event is intended only for interaction with the SUT to extract code coverage and save it for later usage.

The period of time in which a test execution with parallel code coverage measurement took place is called **test context**. After a test context, the measured code coverage from an instrumented SUT can be transmitted and stored on the system for further analysis. It makes sense to pause the test execution until the coverage has been completely transmitted. After completion of the handler, your CANoe DE product continues to execute the test.

See Code Coverage Measurement.

The event is triggered when a test context is terminated. It concerns the leaf elements of the test execution tree, i.e., test case or test sequence.

Within the event, the following information can be used via the **this** operator:

- **this.Name**  
  Name of the test context which is completed, e.g., the test case name or the test sequence name.

- **this.MeasurementId**  
  Unique ID of the measurement. This information and the **this.TestContextRunId** is needed to map the test results in a CANoe DE product report to the measured coverage.

- **this.TestContextRunId**  
  ID of the test context within a measurement. This information and the **this.MeasurementId** is needed to map the test results in a CANoe DE product report to the measured coverage.

The event is supported for Test Units only.

**Note**  
When the event is triggered, you are no longer in the context of a test case. Therefore no tests of the SUT functionality may take place. The event is intended only for the interaction with the SUT to extract code coverage and to save it for later usage. Therefore, no CAPL test commands may be called in the event.

**Example**  
In the following example, the coverage data transfer is done via CAN messages. A specific CAN message within the **on testContextCompleted** event triggers the SUT to transfer the coverage data. After the successful transfer (recognizable by another CAN message), the test execution is continued:

```plaintext
variables
{
  message 0x7FE coverage_sync_message = { DLC = 1 };
  const int cMaxTransferTimeMs = 10000;
}

on testContextCompleted
{
  char result_filename[100];
  long resultTestWaitFor;

  // name of coverage file; this.filename contains the name of the executed test tree element
  strncpy(result_filename, this.Name, elCount(result_filename));
  strncat(result_filename, ".DAT", elCount(result_filename));

  // open the DAT file for writing the coverage data
  open_coverage_file(result_filename);

  // triggers the SUT to send coverage data via CAN message
  coverage_sync_message.dlc = 1;
  coverage_sync_message.byte(0) = 0x00;
  output(coverage_sync_message);

  // wait until the coverage data transfer is completed
  resultTestWaitFor = testWaitForTextEvent("CoverageTransferCompleted", cMaxTransferTimeMs);
  if (resultTestWaitFor == 0) // Timeout
  {
    writeEx(0, 2, "Coverage Data transfer aborted. Reason: Timeout");
  }
}

on message 0x7FF
{
  write_msg_to_inst_file_coverage(this);

  // coverage data transferred completely?
  if (this.byte(0) == 0x01)
  {
    // close DAT file
    close_coverage_file();

    // throw text event to finish TestWaitFor command in ‘on testContextCompleted’ event
    testSupplyTextEvent("CoverageTransferCompleted");
  }
}
```
