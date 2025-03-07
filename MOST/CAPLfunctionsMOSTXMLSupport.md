[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/CAPLfunctionsMOSTXMLSupport.md)

[CAPL Functions](../CAPLfunctions.md) » [MOST](CAPLfunctionsMOSTOverview.md) » General Tips on XML Function Catalog Support in CAPL

# MOST: General Tips on XML Function Catalog Support in CAPL

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE

Tips for using XML-based CAPL functions for the symbolic description of messages and parameters.

There are two different access formats when using XML function catalogs in CAPL:

## Compile Time

- The symbols are checked and resolved during compilation.
- Compile time access is very efficient.

Example:

```plaintext
mostAmsMessage AudioDiskPlayer.TrackPosition.Status msg;
msg.Track = 3;
```

## Runtime

- Since the symbols are interpreted during runtime, this access format is less efficient.
- Faulty symbols cause the measurement process to be aborted.
- Runtime access is the only possible access format for parameters with variable length/position (e.g., strings) and nested parameters (e.g., elements of an array or record).
- For runtime access, symbols have to be enclosed in quotation marks.

Example:

```plaintext
mostAmsOutput(1, "AudioDiskPlayer.SourceActivity.StartResult(1,On)", 1);
testWaitForMostAMSMessage("AudioDiskPlayer.TrackPosition.Status(5)", 1, 200);
mostParamSet(msg, "Data.Record[].LastTrack", idx, 10);
```

[Symbolic Identification of Messages](CAPLfunctionsMOSTSymIDMMessage.md) • [Symbolic Identification of Parameters](CAPLfunctionsMOSTSymIDParam.md) • [Input Assistance](CAPLfunctionsMOSTInputAssistant.md) • [MOST Database Support in CAPL](CAPLfunctionsMOSTDatabaseSupport.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)