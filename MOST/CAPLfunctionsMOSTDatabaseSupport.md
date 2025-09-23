[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/CAPLfunctionsMOSTDatabaseSupport.md)

[CAPL Functions](../CAPLfunctions.md) » [MOST](CAPLfunctionsMOSTOverview.md) » Database Support in CAPL

# MOST: Database Support in CAPL

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE

Symbols from MOST function catalogs can be used in CAPL. The most common applications are outlined on this page.

- [Initializing a MOST message variable](CAPLfunctionsMOSTInitializationMessageVariables.md) and [Sending](Functions/CAPLfunctionMOSToutput.md)

  ```plaintext
  mostAmsMessage AudioDiskPlayer.TrackPosition.Get msg;
  output(msg);
  ```

- Declaration of event procedures (see [on mostMessage](EventProcedures/CAPLfunctionOnMOSTMessage.md) or [on mostAmsMessage](EventProcedures/CAPLfunctionOnMOSTAMSMessage.md))

  ```plaintext
  on mostAmsMessage AudioDiskPlayer.TrackPosition.Status
  {
     ...
  }
  ```

- [Populating simple message parameters with data](CAPLfunctionsMOSTSymIDParam.md). This includes all non-nested parameters in the user data with constant width and constant position.

  ```plaintext
  mostAmsMessage AudioDiskPlayer.TrackPosition.Status msg;
  msg.Track = 5;
  ```

- [Populating complex message parameters with data](CAPLfunctionsMOSTSymIDParam.md) (parameters with variable length/position, all nested parameters):

  ```plaintext
  mostAmsMessage AudioDiskPlayer.MediaInfo.Status msg;
  mostParamSetString(msg, "Data.Record[].MediaTitle", idx, "Rolling Stones");
  mostParamSet(msg, "Data.Record[].LastTrack", idx, 10);
  ```

Since the message data is dynamic, the parameter address ("Data.Record[].MediaTitle") cannot be checked until runtime.

- Symbols from enumeration types can be indicated with the addition of message names and parameter names.

  ```plaintext
  mostAmsMessage AudioDiskPlayer.Random.Status msg;
  msg.RandomState = AudioDiskPlayer.Random.Status.RandomState::Off;
  ```

- Functions of test feature sets for MOST

  ```plaintext
  if(1 == TestWaitForMostAMSMessage("AudioDiskPlayer.TrackPosition.Status(5)", 1, 200))
  TestStepPass("1", "TrackPosition=5 reported");
  ```

- Complete data population of messages ([mostMsgSet](Functions/CAPLfunctionMOSTMsgSet.md), [mostAmsOutput](Functions/CAPLfunctionMOSTAmsOutput.md))

  ```plaintext
  mostMsgSet(msg, "AudioDiskPlayer.SourceActivity.StartResult(1,On)", 1);
  or
  mostAmsOutput(1, "AudioDiskPlayer.SourceActivity.StartResult(1,On)", 1);
  ```

[General Tips on XML Function Catalog Support in CAPL](CAPLfunctionsMOSTXMLSupport.md) • [Input Assistant](CAPLfunctionsMOSTInputAssistant.md) • [MOST: Symbolic Identification of Messages](CAPLfunctionsMOSTSymIDMMessage.md) • [MOST: Symbolic Identification of Parameters](CAPLfunctionsMOSTSymIDParam.md) • [Selectors](Selectors/CAPLfunctionMOSTSelectors.md)
