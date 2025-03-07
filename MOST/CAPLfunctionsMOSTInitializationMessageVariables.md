[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/CAPLfunctionsMOSTInitializationMessageVariables.md)

**CAPL Functions** » [MOST](CAPLfunctionsMOSTOverview.md) » Initialization of message variables

# MOST: Initialization of Message Variables

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

There are the following types of message variable for MOST:

- **mostMessage**: Variables describe MOST frames which are compliant with the function catalog.

  **Example**  
  With XML function catalog support:  
  `mostMessage NetBlock.FBlockIDs.Get msg;`  
  With CANdb database support:  
  `mostMessage NetBlock_FBlockIDs_Get msg;`  

  `mostMessage * msg;` // Initialization with wildcard -> The parameters FBlockID..OpType have to be set explicitly ([msg.FBlockID, msg.InstanceID, msg.FunctionID, msg.OpType](Selectors/CAPLfunctionMOSTSelectors.md))  
  `mostMessage 0x010001 msg;` // Initialization with FBlockID..OpType (see also [Message-ID](../../CANoeCANalyzer/MOST/MOSTDatabaseCANdb.md))

- **mostRawMessage**: Variables describe MOST frames which do not fit into the function catalog structure (e.g., RemRead, RemWrite, Alloc, Dealloc, GetSource for MOST25).

- **mostAMSMessage**: Variables describe Application Message Service (AMS) messages. These messages comply with the function catalog format and - like mostMessage variables - they can be identified by an [ID](../../CANoeCANalyzer/MOST/MOSTDatabaseCANdb.md).

  **Example**  
  With XML function catalog support:  
  `mostAMSMessage NetBlock.FBlockIDs.Get msg;`  
  With CANdb database support:  
  `mostAMSMessage NetBlock_FBlockIDs_Get msg;`  

  `mostAMSMessage * msg;` // Initialization with wildcard -> The parameters FBlockID..OpType have to be set explicitly (msg.FBlockID, msg.InstanceID, msg.FunctionID, msg.OpType)  
  `mostAMSMessage 0x010001 msg;` // Initialization with FBlockID..OpType (see also [Message-ID](../../CANoeCANalyzer/MOST/MOSTDatabaseCANdb.md))

  **The default size of mostAMSMessage variables is 200 bytes**. To define messages with larger useful data ranges the desired size must be specified explicitly:  
  `mostAMSMessage * msg = { DLC = 1000 };`  
  Before sending the message with output(msg) the DLC and thereby also the TelLen can be updated according to the length actually set.

**Example**  
Press <Ctrl>+<M> or select **Message entry with MOST function catalog** from the shortcut menu to open an input assistant which displays a data entry field in the current program line listing a selection of all MOST messages described in the function catalog. The selection takes in all function catalogs assigned to the CAPL node.

In this context, the input assistant enables the description of messages up to **OpType** and adds the resulting description to the program text without quotation marks in the notation separated by period marks.

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)