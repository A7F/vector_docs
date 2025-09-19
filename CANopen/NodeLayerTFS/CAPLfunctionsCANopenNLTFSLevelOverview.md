# CANopen Test Feature Set Node Layer CAPL Functions

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

To use the CAPL functions the node layer **CANopenTfsNl.dll** must be included. You can include the node layer by using the configuration dialog of the node on page **Components** or via the node attribute **NodeLayerModules** in the database.

**ON THIS PAGE:**

- [Level 1](#Level1)
  - [Guarding](#GuardingL1)
  - [Heartbeat](#HeartbeatL1)
  - [NMT](#NMTL1)
  - [SDO](#SDOL1)
- [Level 2](#Level2)
  - [EMCY](#EMCYL2)
  - [Guarding](#GuardingL2)
  - [Heartbeat](#HeartbeatL2)
  - [Monitoring](#MonitoringL2)
  - [NMT](#NMTL2)
  - [Object Dictionary](#ObjectDictL2)
  - [SDO](#SDOL2)
  - [SDO Abort](#SDOabortL2)
  - [SYNC](#SYNCL2)
  - [TPDO](#TPDOL2)
  - [LSS](#LSSL2)
- [Level 3](#Level3)
  - [Guarding](#GuardingL3)
  - [Heartbeat](#HeartbeatL3)
  - [NMT](#NMTL3)
  - [Object Dictionary](#ObjectDictL3)
  - [SDO](#SDOL3)
  - [SYNC](#SYNCL3)
- [Test Control](#TestControl)
  - [Check](#Check_functions)
  - [Parameter Control](#ParameterControl)
  - [Test Configurator](#TestConfiguratorFunctions)

## Level 1 [▲ back](#Shortcuts)

Enable the generation of CANopen protocol errors at any point and the exploitation of limit cases. The user is responsible for the communication here and can also write complete tests himself. Of course the mixing of the functions of the individual test levels is also possible.

This section contains a brief listing of all Level 1 functions that are made available by the CANopen Test Feature Set node layer.

### Guarding [▲ back](#Shortcuts)

- [coTfsGuardingRequest](Functions/CAPLfunctionCoTfsGuardingRequest.md): Sends an user-definable guarding request.

### Heartbeat [▲ back](#Shortcuts)

- [coTfsHeartbeatProducerCheckIfActive](Functions/CAPLfunctionCoTfsHeartbeatProducerCheckIfActive.md): Returns the current status of the heartbeat producer of the selected node. If this is switched on, the time settings are checked (passive test).

### NMT [▲ back](#Shortcuts)

- [coTfsNMTRequest](Functions/CAPLfunctionCoTfsNmtRequest.md): NMT request
- [coTfsNmtGetCurrentState](Functions/CAPLfunctionCoTfsNmtGetCurrentState.md): Returns the current device state.

### SDO [▲ back](#Shortcuts)

- [coTfsSDOCalcCrc](Functions/CAPLfunctionCoTfsSdoCalcCrc.md): Calculates the CRC checksum for a block transfer.
- [coTfsSDOGetBlockSize](Functions/CAPLfunctionCoTfsSdoGetBlockSize.md): Returns the block size that is used for a block transfer.
- [coTfsSDOBlockInit](Functions/CAPLfunctionCoTfsSdoBlockInit.md): Starts a SDO block up/download.
- [coTfsSDOBlockEnd](Functions/CAPLfunctionCoTfsSdoBlockEnd.md): Stops a SDO block up/download.
- [coTfsSDOBlockDownloadSegmentRequest](Functions/CAPLfunctionCoTfsSdoBlockDownloadSegmentRequest.md): Sends an individual segment of a SDO block download.
- [coTfsSDOBlockUploadSegmentResponse](Functions/CAPLfunctionCoTfsSdoBlockUploadSegmentResponse.md): Sends the response to a SDO upload block request.
- [coTfsSdoBlockUploadGetCRC](Functions/CAPLfunctionCoTfsSdoBlockUploadGetCRC.md): Gets the CRC checksum of last successful SDO block upload.
- [coTfsSDOSegmentRequest](Functions/CAPLfunctionCoTfsSdoSegmentRequest.md): Sends an individual data segment of a segmented SDO transfer.
- [coTfsSDOChkCrcSupport](Functions/CAPLfunctionCoTfsSdoChkCrcSupport.md): Returns the CRC support flag of a SDO init block download response.
- [coTfsSDOInit](Functions/CAPLfunctionCoTfsSdoInit.md): Starts an expedited/segmented SDO data transfer.
- [coTfsSDOGetUploadData](Functions/CAPLfunctionCoTfsSdoGetUploadData.md): Returns the received SDO data of an expedited/segmented/block upload.
- [coTfsSDOGetUploadSize](Functions/CAPLfunctionCoTfsSdoGetUploadSize.md): Returns the size of the received SDO data of an expedited/segmented/block upload.
- [coTfsSDOAbort](Functions/CAPLfunctionCoTfsSdoAbort.md): Sends an individual SDO abort message.
- [coTfsSDOInjectRawMsg](Functions/CAPLfunctionCoTfsSdoInjectRawMsg.md): Inserts a CAN message to the following command.
- [coTfsSDOInjectAbortMsg](Functions/CAPLfunctionCoTfsSdoInjectAbortMsg.md): Inserts a SDO abort message to the following command.

## Level 2 [▲ back](#Shortcuts)

Offer the experienced user the setting of some more complex tests. General data access is possible here.

This section contains a brief listing of all Level 2 functions that are made available by the CANopen Test Feature Set node layer.

### EMCY [▲ back](#Shortcuts)

- [coTfsEmcySendMessage](Functions/CAPLfunctionCoTfsEmcySendMessage.md): Sends an emergency message.
- [coTfsEmcyResetList](Functions/CAPLfunctionCoTfsEmcyResetList.md): Removes all entries (of a node) from the internally-stored list.
- [coTfsEmcyWaitForMessage](Functions/CAPLfunctionCoTfsEmcyWaitForMessage.md): Waits for an emergency message of a particular node.
- [coTfsEmcyGetErrorCode](Functions/CAPLfunctionCoTfsEmcyGetErrorCode.md): Returns received emergency messages (of a node).

### Guarding [▲ back](#Shortcuts)

- [coTfsNodeGuarding](Functions/CAPLfunctionCoTfsNodeGuarding.md): Starts a node guarding test.
- [coTfsLifeGuarding](Functions/CAPLfunctionCoTfsLifeGuarding.md): Starts a life guarding test.

### Heartbeat [▲ back](#Shortcuts)

- [coTfsHeartbeatConsumer](Functions/CAPLfunctionCoTfsHeartbeatConsumer.md): A test is executed for a heartbeat consumer.
- [coTfsHeartbeatProducer](Functions/CAPLfunctionCoTfsHeartbeatProducer.md): The heartbeat producer of a CANopen® device is checked.

### Monitoring [▲ back](#Shortcuts)

- [coTfsMonitorActivate](Functions/CAPLfunctionCoTfsMonitorActivate.md): Activates the passive communication monitor.
- [coTfsMonitorDeactivate](Functions/CAPLfunctionCoTfsMonitorDeactivate.md): Deactivates the passive communication monitor.
- [coTfsMonitorExcludeNodeId](Functions/CAPLfunctionCoTfsMonitorExcludeNodeId.md): Excludes a single node-ID from monitoring.
- [coTfsMonitorExcludeNodeIdRange](Functions/CAPLfunctionCoTfsMonitorExcludeNodeIdRange.md): Excludes a range of node-IDs from monitoring.
- [coTfsMonitorIncludeNodeId](Functions/CAPLfunctionCoTfsMonitorIncludeNodeId.md): Includes a single node-ID for monitoring.
- [coTfsMonitorIncludeNodeIdRange](Functions/CAPLfunctionCoTfsMonitorIncludeNodeIdRange.md): Includes a range of node-IDs for monitoring.
- [coTfsMonitorSetLssTimeout](Functions/CAPLfunctionCoTfsMonitorSetLssTimeout.md): Sets the LSS timeout for the passive communication monitor.
- [coTfsMonitorSetNmtTimeout](Functions/CAPLfunctionCoTfsMonitorSetNmtTimeout.md): Sets the NMT timeout for the passive communication monitor.
- [coTfsMonitorSetSdoTimeout](Functions/CAPLfunctionCoTfsMonitorSetSdoTimeout.md): Sets the SDO timeout for the passive communication monitor.
- [coTfsCbGetReferenceTime](Functions/CAPLfunctionCoTfsCbGetReferenceTime.md): Gets the maximum, minimum, and average value of an active monitor.
- [coTfsCbGetSettings](Functions/CAPLfunctionCoTfsCbGetSettings.md): Gets parameter of an active monitor.
- [coTfsConfigureGenericMonitor](Functions/CAPLfunctionCoTfsConfigureGenericMonitor.md): Configures and activates a generic message monitor.
- [coTfsDeactivateGenericMonitor](Functions/CAPLfunctionCoTfsDeactivateGenericMonitor.md): Stops a generic message monitor and evaluate monitoring results.
- [coTfsCheckAndCompareGenericMonitorMessage](Functions/CAPLfunctionCoTfsCheckAndCompareGenericMonitorMessage.md): Checks if the expected message data are received during a generic message monitoring.
- [coTfsMonitorGetStatistics](Functions/CAPLfunctionCoTfsMonitorGetStatistics.md): Returns statistics information.

### NMT [▲ back](#Shortcuts)

- [coTfsNMTEnterPreOperational](Functions/CAPLfunctionCoTfsNmtEnterPreOperational.md): The DUT is set to state "Pre-Operational".
- [coTfsNMTResetCommunication](Functions/CAPLfunctionCoTfsNmtResetCommunication.md): The DUT is commanded to execute a "Reset Communication".
- [coTfsNMTResetNode](Functions/CAPLfunctionCoTfsNmtResetNode.md): The DUT is commanded to execute a "Reset Node".
- [coTfsNMTStartNode](Functions/CAPLfunctionCoTfsNmtStartNode.md): The DUT is set to state "Operational".
- [coTfsNMTStopNode](Functions/CAPLfunctionCoTfsNmtStopNode.md): The DUT is set to state "Stopped".
- [coTfsNmtWaitForBootupMessage](Functions/CAPLfunctionCoTfsNmtWaitForBootupMessage.md): The DUT waits for a NMT boot-up message.

### Object Dictionary [▲ back](#Shortcuts)

- [coTfsODAddEntry](Functions/CAPLfunctionCoTfsOdAddEntry.md): Adds a single object to the internal list of test objects.
- [coTfsODAddEntryIndexRange](Functions/CAPLfunctionCoTfsOdAddEntryIndexRange.md): Adds a list of object entries to the internal list, which only differ in the given index.
- [coTfsODAddEntrySubIndexRange](Functions/CAPLfunctionCoTfsOdAddEntrySubIndexRange.md): Adds a list of object entries to the internal list, which only differ in the given subindex.
- [coTfsODAddOptEntryValueRange](Functions/CAPLfunctionCoTfsOdAddOptEntryValueRange.md): Expands the allowed value range of the last created object entry.
- [coTfsODAddOptEntryValue](Functions/CAPLfunctionCoTfsOdAddOptEntryValue.md): Expands the allowed value range of the last created object entry with a given value.
- [coTfsODChkSingleEntry](Functions/CAPLfunctionCoTfsOdChkSingleEntry.md): Checks a single object dictionary entry of existence and size via a SDO upload.
- [coTfsODChkSingleEntryNotExist](Functions/CAPLfunctionCoTfsOdChkSingleEntryNotExist.md): Checks if the given object does not exist in the object dictionary.
- [coTfsODClearAllEntries](Functions/CAPLfunctionCoTfsOdClearAllEntries.md): Deletes all objects of the internal test object list.
- [coTfsODChkNotExist](Functions/CAPLfunctionCoTfsOdChkNotExist.md): Executes an user defined object dictionary test on hidden objects.
- [coTfsODChk](Functions/CAPLfunctionCoTfsOdChk.md): Executes an user defined object dictionary test considering access type, data type and default values.
- [coTfsODSetErrorHandling](Functions/CAPLfunctionCoTfsOdSetErrorHandling.md): Controls the abort behavior of the test module.

### SDO [▲ back](#Shortcuts)

- [coTfsSDOBlockDownload](Functions/CAPLfunctionCoTfsSdoBlockDownload.md): Executes a complete SDO block download.
- [coTfsSDOBlockUpload](Functions/CAPLfunctionCoTfsSdoBlockUpload.md): Executes a complete SDO block upload.
- [coTfsSDOUpload](Functions/CAPLfunctionCoTfsSdoUpload.md): Executes a SDO upload.
- [coTfsSDODownload](Functions/CAPLfunctionCoTfsSdoDownload.md): Executes a SDO download.
- [coTfsSDOUploadAndCompare](Functions/CAPLfunctionCoTfsSdoUploadAndCompare.md): Executes a SDO upload. The data received are checked against predefined data.
- [coTfsSDODownloadUploadAndCompare](Functions/CAPLfunctionCoTfsSdoDownloadUploadAndCompare.md): Executes a SDO download, followed by a SDO upload. The data received are checked against predefined data.
- [coTfsSDOGetUploadData](Functions/CAPLfunctionCoTfsSdoGetUploadData.md): Returns the received SDO data of an expedited/segmented/block upload.
- [coTfsSDOGetUploadSize](Functions/CAPLfunctionCoTfsSdoGetUploadSize.md): Returns the size of the received SDO data of an expedited/segmented/block upload.
- [coTfsSDOAbortTest](Functions/CAPLfunctionCoTfsSdoAbortTest.md): Stops a test after a specified number of CAN messages.
- [coTfsSdoChkEntryExists](Functions/CAPLfunctionCoTfsSdoChkEntryExists.md): Checks if an object is readable.

### SDO Abort [▲ back](#Shortcuts)

- [coTfsSDOWaitForAbortCode](Functions/CAPLfunctionCoTfsSdoWaitForAbortCode.md): Waits for the occurrence of a SDO abort message from a particular node.
- [coTfsSDOWaitForSpecificAbortCode](Functions/CAPLfunctionCoTfsSdoWaitForSpecificAbortCode.md): Wait for specific SDO abort codes.
- [coTfsSDOGetAbortCode](Functions/CAPLfunctionCoTfsSdoGetAbortCode.md): Returns the received SDO abort code.
- [coTfsSDOAddAccAbortCode](Functions/CAPLfunctionCoTfsSdoAddAccAbortCode.md): Adds a specific abort code to the internal list of accepted abort codes.
- [coTfsSDOAbortCodeOccured](Functions/CAPLfunctionCoTfsSdoAbortCodeOccured.md): Checks for successful execution of a SDO command with a valid SDO abort code.
- [coTfsSdoChkForUnexpectedAbort](Functions/CAPLfunctionCoTfsSdoChkForUnexpectedAbort.md): Checks for unexpected SDO abort codes.

### SYNC [▲ back](#Shortcuts)

- [coTfsSyncProducerDetail](Functions/CAPLfunctionCoTfsSyncProducerDetail.md): Starts a freely-configurable SYNC producer test. This test requires the existence of the optional sync counter.

### TPDO [▲ back](#Shortcuts)

- [coTfsTPDOGetDataBySyncCyclic](Functions/CAPLfunctionCoTfsTpdoGetDataBySyncCyclic.md): Configures a TPDO as cyclic and starts a virtual sync producer. Checks the transmit performance of the test node.
- [coTfsTPDOGetDataByEventTimer](Functions/CAPLfunctionCoTfsTpdoGetDataByEventTimer.md): Configures the event timer of the TPDO and check the transmit cycle.
- [coTfsTPDOGetDataByRTR](Functions/CAPLfunctionCoTfsTpdoGetDataByRtr.md): Gets the COB-ID and transmit the TPDO data read with a remote frame.

### LSS [▲ back](#Shortcuts)

- [coTfsLssSendSwitchStateModeGlobalRequest](Functions/CAPLfunctionCoTfsLssSendSwitchStateModeGlobalMsg.md): Sends a Switch state global LSS mode message.
- [coTfsLssWaitForSwitchStateModeGlobalRequest](Functions/CAPLfunctionCoTfsLssWaitForSwitchStateModeGlobalMsgReq.md): Waits for a Switch state global LSS mode message.
- [coTfsLssSendSwitchStateSelectiveSequence](Functions/CAPLfunctionCoTfsLssSendSwitchStateSelectiveSeq.md): Sends a Switch state selective messages and waits for the response.
- [coTfsLssWaitforSwitchStateSelectiveSequence](Functions/CAPLfunctionCoTfsLssWaitForSwitchStateSelectiveSeq.md): Waits for a Switch state selective messages and sends the response.
- [coTfsLssSendConfigureNodeIdRequest](Functions/CAPLfunctionCoTfsLssSendConfNodeIdReq.md): Sends a Configure LSS node-ID request and waits for the response.
- [coTfsLssSendConfigureNodeIdResponse](Functions/CAPLfunctionCoTfsLssSendConfNodeIdResp.md): Sends the LSS Configure node-ID response.
- [coTfsLssSendConfigureBitTimingRequest](Functions/CAPLfunctionCoTfsLssSendConfBitTimingReq.md): Sends a Configure LSS bit timing parameters request and waits for the response.
- [coTfsLssWaitForConfigureBitTimingRequest](Functions/CAPLfunctionCoTfsLssWaitForConfBitTimingReq.md): Waits for Configure LSS bit timing parameters request.
- [coTfsLssSendConfigureBitTimingResponse](Functions/CAPLfunctionCoTfsLssSendConfBitTimingResp.md): Sends the Configure LSS bit timing parameters response.
- [coTfsLssSendActivateBitTimingRequest](Functions/CAPLfunctionCoTfsLssSendActBitTimingParReq.md): Sends an Activate LSS bit timing parameter request.
- [coTfsLssWaitForActivateBitTimingRequest](Functions/CAPLfunctionCoTfsLssWaitForActBitTimingParReq.md): Waits for an Activate LSS bit timing parameter request.
- [coTfsLssSendStoreConfigurationRequest](Functions/CAPLfunctionCoTfsLssSendStoreConfReq.md): Sends a LSS Store Configuration request and waits for the response.
- [coTfsLssWaitForStoreConfigurationRequest](Functions/CAPLfunctionCoTfsLssWaitForStoreConfReq.md): Waits for the LSS store configuration request and sends the response.
- [coTfsLssSendInquireNodeIdRequest](Functions/CAPLfunctionCoTfsLssSendInquireNodeIdReq.md): Sends an Inquire node-ID request and waits for the response.
- [coTfsLssWaitForInquireNodeIdRequest](Functions/CAPLfunctionCoTfsLssWaitForInquireNodeIdReq.md): Waits for the Inquire node-ID request and sends the response.
- [coTfsLssSendInquireVendorIdRequest](Functions/CAPLfunctionCoTfsLssSendInquireVendorIdReq.md): Sends an Inquire vendor-ID request and waits for the response.
- [coTfsLssWaitForInquireVendorIdRequest](Functions/CAPLfunctionCoTfsLssWaitForInquireVendorIdReq.md): Waits for the Inquire vendor-ID request and sends the response.
- [coTfsLssSendInquireProductCodeRequest](Functions/CAPLfunctionCoTfsLssSendInquireProductCodeReq.md): Sends an Inquire product code request and waits for the response.
- [coTfsLssWaitForInquireProductCodeRequest](Functions/CAPLfunctionCoTfsLssWaitForInquireProductCodeReq.md): Waits for the Inquire product code request and sends the response.
- [coTfsLssSendInquireRevisionNoRequest](Functions/CAPLfunctionCoTfsLssSendInquireRevisionNoReq.md): Sends an Inquire revision number request and waits for the response.
- [coTfsLssWaitForInquireRevisionNoRequest](Functions/CAPLfunctionCoTfsLssWaitForInquireRevisionNoReq.md): Waits for the Inquire revision number request and sends the response.
- [coTfsLssSendInquireSerialNoRequest](Functions/CAPLfunctionCoTfsLssSendInquireSerialNoReq.md): Sends an Inquire serial number request and waits for the response.
- [coTfsLssWaitForInquireSerialNoRequest](Functions/CAPLfunctionCoTfsLssWaitForInquireSerialNoReq.md): Waits for the Inquire serial number request and sends the response
- [coTfsLssSendIdentifyRemoteSlaveSequence](Functions/CAPLfunctionCoTfsLssSendIdentifyRemoteSlaveSeq.md): Sends a LSS identify remote slave sequence.
- [coTfsLssWaitForIdentifyRemoteSlaveSequence](Functions/CAPLfunctionCoTfsLssWaitForIdentifyRemoteSlaveSeq.md): Waits for a LSS identify remote slave sequence.
- [coTfsLssSendIdentifySlaveResponse](Functions/CAPLfunctionCoTfsLssSendIdentifySlaveResp.md): Sends an Identify slave protocol response message.
- [coTfsLssWaitForIdentifySlaveResponse](Functions/CAPLfunctionCoTfsLssWaitForIdentifySlaveResp.md): Waits for the Identify slave protocol response message.
- [coTfsLssSendIdentifyNonConfRemoteSlaveRequest](Functions/CAPLfunctionCoTfsLssSendIdentifyNonConfRemoteSlaveReq.md): Sends an Identify non-configured remote slave response.
- [coTfsLssWaitForIdentifyNonConfRemoteSlaveRequest](Functions/CAPLfunctionCoTfsLssWaitForIdentifyNonConfRemoteSlaveReq.md): Waits for an Identify non-configured remote slave response.
- [coTfsLssSendIdentifyNonConfSlaveResponse](Functions/CAPLfunctionCoTfsLssSendIdentifyNonConfSlaveResp.md): Sends an Identify non-configured remote slave response.
- [coTfsLssWaitForIdentifyNonConflaveResponse](Functions/CAPLfunctionCoTfsLssWaitForIdentifyNonConfSlaveResp.md): Waits for an Identify non-configured slave response.
- [coTfsLssSendFastScanRequest](Functions/CAPLfunctionCoTfsLssSendFastScanReq.md): Sends a LSS FastScan protocol request.
- [coTfsLssWaitForFastScanRequest](Functions/CAPLfunctionCoTfsLssWaitForFastScanReq.md): Waits for the FastScan message.
- [coTfsLssWaitForMasterRequestMessage](Functions/CAPLfunctionCoTfsLssWaitForMasterRequestMessage.md): Waits for a configured LSS Master request.
- [coTfsLssAddMasterResponseSwitchStateSelective](Functions/CAPLfunctionCoTfsLssAddMasterResponseSwitchStateSelective.md): Adds a LSS Master request wait condition to the internal list.
- [coTfsLssAddMasterResponseSwitchStateGlobal](Functions/CAPLfunctionCoTfsLssAddMasterResponseSwitchStateGlobal.md): Adds a LSS Master request wait condition to the internal list.
- [coTfsLssAddMasterResponseConfigureNodeId](Functions/CAPLfunctionCoTfsLssAddMasterResponseConfigureNodeId.md): Adds a LSS Master request wait condition to the internal list.
- [coTfsLssAddMasterResponseConfigureBitTiming](Functions/CAPLfunctionCoTfsLssAddMasterResponseConfigureBitTiming.md): Adds a LSS Master request wait condition to the internal list.
- [coTfsLssAddMasterResponseActivateBitTiming](Functions/CAPLfunctionCoTfsLssAddMasterResponseActivateBitTiming.md): Adds a LSS Master request wait condition to the internal list.
- [coTfsLssAddMasterResponseStoreConfiguration](Functions/CAPLfunctionCoTfsLssAddMasterResponseStoreConfiguration.md): Adds a LSS Master request wait condition to the internal list.
- [coTfsLssAddMasterResponseInquireNodeId](Functions/CAPLfunctionCoTfsLssAddMasterResponseInquireNodeId.md): Adds a LSS Master request wait condition to the internal list.
- [coTfsLssAddMasterResponseInquireProductCode](Functions/CAPLfunctionCoTfsLssAddMasterResponseInquireProductCode.md): Adds a LSS Master request wait condition to the internal list.
- [coTfsLssAddMasterResponseInquireRevisionNo](Functions/CAPLfunctionCoTfsLssAddMasterResponseInquireRevisionNo.md): Adds a LSS Master request wait condition to the internal list.
- [coTfsLssAddMasterResponseInquireSerialNo](Functions/CAPLfunctionCoTfsLssAddMasterResponseInquireSerialNo.md): Adds a LSS Master request wait condition to the internal list.
- [coTfsLssAddMasterResponseInquireVendorId](Functions/CAPLfunctionCoTfsLssAddMasterResponseInquireVendorId.md): Adds a LSS Master request wait condition to the internal list.
- [coTfsLssAddMasterResponseIdentifyNonConfRemoteSlv](Functions/CAPLfunctionCoTfsLssAddMasterResponseIdentifyNonConfRemoteSlv.md): Adds a LSS Master request wait condition to the internal list.
- [coTfsLssAddMasterResponseIdentifyFastscan](Functions/CAPLfunctionCoTfsLssAddMasterResponseIdentifyFastscan.md): Adds a LSS Master request wait condition to the internal list.
- [coTfsLssSetMasterResponseIdentifyRemoteSlaveMask](Functions/CAPLfunctionCoTfsLssSetMasterResponseIdentifyRemoteSlaveMask.md): Sets the bitmasks for using the function [coTfsLssAddMasterResponseIdentifyNonConfRemoteSlv](Functions/CAPLfunctionCoTfsLssAddMasterResponseIdentifyNonConfRemoteSlv.md).

## Level 3 [▲ back](#Shortcuts)

Can be implemented very easily and require only a little CANopen knowledge. With these tests, it is possible to check the absolute basic functionality of the DUT in the simplest way.

This section contains a brief listing of all Level 3 functions that are made available by the CANopen Test Feature Set node layer.

### Guarding [▲ back](#Shortcuts)

- [coTfsGuarding](Functions/CAPLfunctionCoTfsGuarding.md): Executes a simple guarding test.

### Heartbeat [▲ back](#Shortcuts)

- [coTfsHeartbeat](Functions/CAPLfunctionCoTfsHeartBeat.md): Executes a complete heartbeat producer and heartbeat consumer test with different time settings.

### NMT [▲ back](#Shortcuts)

- [coTfsNMT](Functions/CAPLfunctionCoTfsNmt.md): Executes a simple NMT test.

### Object Dictionary [▲ back](#Shortcuts)

- [coTfsODCheckStdEntries](Functions/CAPLfunctionCoTfsOdChkStdEntries.md): Checks standard entries of the object dictionary.

### SDO [▲ back](#Shortcuts)

- [coTfsSDO](Functions/CAPLfunctionCoTfsSdo.md): Executes an expedited/segmented/block download/upload test.

### SYNC [▲ back](#Shortcuts)

- [coTfsSyncProducer](Functions/CAPLfunctionCotfsSyncProducer.md): Starts a SYNC producer test.

## Test Control [▲ back](#Shortcuts)

Make help functionality available to the user in order to describe the desired tests more easily and quickly.

- This section offers a brief overview of the additional functions for test control of the CANopen TFS node layer.
- This section offers a brief overview of the additional functions for test control of the CANopen TFS node layer.

### Check [▲ back](#Shortcuts)

- [coTfsActivateGuardingReqMonitor](Functions/CAPLfunctionCoTfsActivateGuardingReqMonitor.md): Checks the temporally correct occurrence of guarding RTRs and controls the corresponding callback functions.
- [coTfsActivateHeartbeatMonitor](Functions/CAPLfunctionCoTfsActivateHeartbeatMonitor.md): Checks the temporally correct occurrence of the heartbeat producer message and calls the corresponding callback functions.
- [coTfsActivateSyncMonitor](Functions/CAPLfunctionCoTfsActivateSyncMonitor.md): Checks the temporally correct occurrence of the SYNC message and calls the corresponding callback functions.
- [coTfsActivateSyncPdoMonitor](Functions/CAPLfunctionCoTfsActivateSyncPdoMonitor.md): Checks the temporally correct occurrence of SYNC PDO messages and calls the corresponding callback functions.
- [coTfsDeactivateGuardingReqMonitor](Functions/CAPLfunctionCoTfsDeactivateGuardingReqMonitor.md): Switches off the checking of guarding RTRs.
- [coTfsDeactivateHeartbeatMonitor](Functions/CAPLfunctionCoTfsDeactivateHeartbeatMonitor.md): Switches off the checking of the heartbeat producer.
- [coTfsDeactivateSyncMonitor](Functions/CAPLfunctionCoTfsDeactivateSyncMonitor.md): Switches off the checking of the SYNC messages.
- [coTfsDeactivateSyncPdoMonitor](Functions/CAPLfunctionCoTfsDeactivateSyncPdoMonitor.md): Switches off the checking of the SYNC PDO messages.

### Parameter Control [▲ back](#Shortcuts)

- [coTfsGetNodeId](Functions/CAPLfunctionCoTfsGetNodeId.md): Transfers the internally-stored node-ID.
- [coTfsSetNodeId](Functions/CAPLfunctionCoTfsSetNodeId.md): Sets the internally-stored node-ID.
- [coTfsSetSdoCANid](Functions/CAPLfunctionCoTfsSetsDocAnId.md): Sets the CAN identifier to be used for the SDO tests.

### Test Configurator [▲ back](#Shortcuts)

- InitializeTestSystem: This function can be used to set common test settings by calling simple test functions as follows.
  - The functions [coTfsSDOResetAbortList](Functions/CAPLfunctionCoTfsSdoResetAbortList.md), [coTfsSDOResetAccAbortList](Functions/CAPLfunctionCoTfsSdoResetAccAbortList.md), [coTfsEmcyResetList](Functions/CAPLfunctionCoTfsEmcyResetList.md), and [coTfsODClearAllEntries](Functions/CAPLfunctionCoTfsOdClearAllEntries.md) are executed if this function is called.
  - The function [coTfsNMTRequest](Functions/CAPLfunctionCoTfsNmtRequest.md) is executed only if it is specified via the parameter sendNMTCmd.
  - The functions [coTfsSetNodeId](Functions/CAPLfunctionCoTfsSetNodeId.md), [coTfsLoadDeviceDescription](Functions/CAPLfunctionCoTfsLoadDeviceDescription.md), [coTfsSetTimeoutValue](Functions/CAPLfunctionCoTfsSetTimeOutValue.md), and [coTfsSetReportBehaviour](Functions/CAPLfunctionCoTfsSetReportBehaviour.md) are executed only if the function was not executed before or the respective parameter value has changed.
- SendCANMessage: This function sends a simple CAN frame by using the CAPL function [output](../../CAN/Functions/CAPLfunctionOutput.md).
- StartBackgroundBusload: This function starts transmission of messages that produces a specified busload. With the parameter `baudRate` and `busTrafficCategory` a definite CANoe log file is defined according to CiA® TR308. The message sequences of that file are replayed during measurement.
- StopBackgroundBusload: This function calls CAPL function [StopReplayFile](../../Other/Functions/CAPLfunctionStopReplayFile.md) to stop an active generation of busload that has been started with `StartBackgroundBusload`.
- TestWaitForTesterConfirmation: This function displays a window that shows the string to the tester. The tester can acknowledge the window with `yes` or `no`.
- UserDefinedFunction: This function calls the customizable CAPL test function. The customizable function may be defined in a separated CAPL file and this file can be inserted in the Include program section via the syntax #include.
- WriteTextInReport: This function writes the given text into report.

[Test Feature Set Error Codes](CAPLfunctionsCANopenNLTFSErrorCodes.md) • [Constants Used in the CAPL Examples](CAPLfunctionsCANopenNLTFSExampleConstants.md) • [Checked Objects](CAPLfunctionsCANopenNLTFSCoTfsOdChkStdEntriesObjects.md)
