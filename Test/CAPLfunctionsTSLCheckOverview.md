# Test Service Library: Checks

[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/CAPLfunctionsTSLCheckOverview.md)

**CAPL Functions** » **Test Service Library** » Check Overview

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

The following [check descriptions](../../TestCommands/CheckDescriptions.md) are available:

- **Absence of FlexRay Erroneous Frames**
  - [TestCheck::CreateFlexRayFrameErrorOccurrenceCount, TestCheck::StartFlexRayFrameErrorOccurrenceCount](Functions/CAPLfunctionTestCheckCreateFlexRayFrameErrorOccurrenceCount.md)
  - [TestCheck::CreateNodeFlexRayFrameErrorsOccurrenceCount, TestCheck::StartNodeFlexRayFrameErrorsOccurrenceCount](Functions/CAPLfunctionTestCheckCreateFlexRayFrameErrorOccurrenceCount.md)
  - Checks the absence of erroneous frames for the specified frame/slot on the bus.

- **Absence of FlexRay Null Frames**
  - [TestCheck::CreateFlexRayNullFrameOccurrenceCount, TestCheck::StartFlexRayNullFrameOccurrenceCount](Functions/CAPLfunctionTestCheckCreateFlexRayNullFrameOccurrenceCount.md)
  - [TestCheck::CreateNodeFlexRayNullFramesOccurrenceCount, TestCheck::StartNodeFlexRayNullFramesOccurrenceCount](Functions/CAPLfunctionTestCheckCreateFlexRayNullFrameOccurrenceCount.md)
  - Checks the absence of Null Frames for the specified frame/slot on the bus.

- **ADAS Detected Objects Distance Observation**
  - [ChkCreate_ADASDetectedObjectsDistanceViolation, ChkStart_ADASDetectedObjectsDistanceViolation](Functions/CAPLfunctionChkCreateADASDetectedObjectsDistanceViolation.md)
  - Observes the distance of the Detected Moving Objects.

- **ADAS Detected Objects Have Matching Ground Truth Objects Observation**
  - [ChkCreate_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation, ChkStart_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation](Functions/CAPLfunctionChkCreateADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation.md)
  - Observes if Detected Moving Objects have matching Moving Objects.

- **ADAS Detected Objects Speed Observation**
  - [ChkCreate_ADASDetectedObjectsSpeedViolation, ChkStart_ADASDetectedObjectsSpeedViolation](Functions/CAPLfunctionChkCreateADASDetectedObjectsSpeedViolation.md)
  - Observes the relative speed of the Detected Moving Objects.

- **ADAS Detected Objects Time To Collision Observation**
  - [ChkCreate_ADASDetectedObjectsTimeToCollisionViolation, ChkStart_ADASDetectedObjectsTimeToCollisionViolation](Functions/CAPLfunctionChkCreateADASDetectedObjectsTimeToCollisionViolation.md)
  - Observes the Time To Collision (TTC) to the Detected Moving Objects.

- **ADAS Ground Truth Objects Distance Observation**
  - [ChkCreate_ADASGroundTruthObjectsDistanceViolation, ChkStart_ADASGroundTruthObjectsDistanceViolation](Functions/CAPLfunctionChkCreateADASGroundTruthObjectsDistanceViolation.md)
  - Observes the distance of the Moving Objects to the EgoVehicle.

- **ADAS EgoLane Observation**
  - [chkCreate_ADASEgoVehicleLaneViolation, chkStart_ADASEgoVehicleLaneViolation](Functions/CAPLfunctionChkCreateADASEgoVehicleLaneViolation.md)
  - Observes the lane of the EgoVehicle.

- **ADAS Ground Truth Have Matching Detected Objects Observation**
  - [ChkCreate_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation, ChkStart_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation](Functions/CAPLfunctionChkCreateADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation.md)
  - Observes if Moving Objects have matching Detected Moving Objects.

- **ADAS Ground Truth Objects Speed Observation**
  - [ChkCreate_ADASGroundTruthObjectsSpeedViolation, chkStart_ADASGroundTruthObjectsSpeedViolation](Functions/CAPLfunctionChkCreateADASGroundTruthObjectsSpeedViolation.md)
  - Observes the relative speed of the Moving Objects to the EgoVehicle.

- **ADAS Ground Truth Objects Time To Collision Observation**
  - [ChkCreate_ADASGroundTruthObjectsTimeToCollisionViolation, ChkStart_ADASGroundTruthObjectsTimeToCollisionViolation](Functions/CAPLfunctionChkCreateADASGroundTruthObjectsTimeToCollisionViolation.md)
  - Observes the Time To Impact (TTI) between Moving Objects and the EgoVehicle.

- **AUTOSAR CRC Observation**
  - [ChkCreate_CRCObservationAsrPDU, ChkStart_CRCObservationAsrPDU](Functions/CAPLFunctionChkCreateCRCObservationAsrPDU.md)
  - This check monitors the CRC of a PDU or a single signal group of a PDU.

- **AUTOSAR SQC Observation**
  - [ChkCreate_SQCObservationAsrPDU, ChkStart_SQCObservationAsrPDU](Functions/CAPLfunctionChkCreateSQCObservationAsrPDU.md)
  - This check monitors the SQC of a PDU or a single signal group of a PDU.

- **AUTOSAR UB Observation**
  - [ChkCreate_UBObservationAsrPDU, ChkStart_UBObservationAsrPDU, ChkCreate_UBObservationAsrSignal, ChkStart_UBObservationAsrSignal](Functions/CAPLfunctionChkCreateUBObservationAsrPDUAsrSignal.md)
  - This check monitors the UB of a PDU, a single signal group of a PDU or a single signal of a PDU.

- **Burst Time Limit**
  - [ChkCreate_BurstTimeLimitViolation, ChkStart_BurstTimeLimitViolation](Functions/CAPLfunctionChkCreateBurstTimeLimitViolation.md)
  - Checks the maximum burst time on a bus.

- **Cycle Time**
  - [ChkCreate_MsgAbsCycleTimeViolation, ChkStart_MsgAbsCycleTimeViolation](Functions/CAPLfunctionChkCreateMsgAbsCycleTimeViolation.md)
  - [ChkCreate_MsgRelCycleTimeViolation, ChkStart_MsgRelCycleTimeViolation](Functions/CAPLfunctionChkCreateMsgRelCycleTimeViolation.md)
  - [ChkCreate_NodeMsgsRelCycleTimeViolation, ChkStart_NodeMsgsRelCycleTimeViolation](Functions/CAPLfunctionChkCreateNodeMsgsRelCycleTimeViolation.md)
  - This check is useful to supervise a particular range in message cycle time changes.

- **DLC**
  - [ChkCreate_InconsistentDLC, ChkStart_InconsistentDLC](Functions/CAPLfunctionChkCreateInconsistentDlc.md)
  - [ChkCreate_InconsistentRxDLC, ChkStart_InconsistentRxDLC](Functions/CAPLfunctionChkCreateInconsistentRxDLC.md)
  - [ChkCreate_InconsistentTxDLC, ChkStart_InconsistentTxDLC](Functions/CAPLfunctionChkCreateInconsistentTxDLC.md)
  - This check monitors the DLC, respectively payload length of a message.

- **Error Frame Count**
  - [ChkCreate_ErrorFramesOccured, ChkStart_ErrorFramesOccured](Functions/CAPLfunctionChkCreateErrorFramesOccured.md)
  - This check is suited to supervise the occurrence of Error Frames on the bus.

- **J1939-76 Functional Safety Check**
  - [ChkCreate_J1939_76_FunctionalSafetyCheck](Functions/CAPLfunctionChkCreateJ193976FunctionalSafetyCheck.md)
  - Observes the J1939-76 functional safety communication.

- **J1939 Address Claiming Check**
  - [ChkCreate_J1939AddressClaimViolation, ChkStart_J1939AddressClaimViolation](Functions/CAPLfunctionChkCreateJ1939AddressClaimViolation.md)
  - Observes the Address Claiming of a J1939 node.

- **J1939 BAM**
  - [ChkCreate_J1939BAM, ChkStart_J1939BAM](Functions/CAPLfunctionChkCreateJ1939BAM.md)
  - Observes the BAM transport protocol.

- **J1939 CAN FD Multi-PG Check**
  - [ChkCreate_J1939_CANFD_MultiPgCheck, ChkStart_J1939_CANFD_MultiPgCheck](Functions/CAPLfunctionChkCreateJ1939CANFDmultiPgCheck.md)
  - This check observes Mutli-PG messages according J1939-22 (CAN FD).

- **J1939 CAN FD TP Check**
  - [ChkCreate_J1939_CANFD_TP_Check, ChkStart_J1939_CANFD_TP_Check](Functions/CAPLfunctionChkCreateJ1939CANFDtpCheck.md)
  - This check observes the RTS/CTS and BAM transport protocol according J1939-22 (CAN FD).

- **J1939 Request Check**
  - [ChkCreate_J1939Request; ChkStart_J1939Request](Functions/CAPLfunctionChkCreateJ1939Request.md)
  - Observes the J1939 Requests (EA00h).

- **J1939 Request2 Check**
  - [ChkCreate_J1939Request2, ChkStart_J1939Request2](Functions/CAPLfunctionChkCreateJ1939Request2.md)
  - Observes the J1939 Request2 (C900h).

- **J1939 RTS/CTS**
  - [ChkCreate_J1939RTSCTS, ChkStart_J1939RTSCTS](Functions/CAPLfunctionChkCreateJ1939RTSCTS.md)
  - Observes the RTS/CTS transport protocol.

- **LIN Baudrate**
  - [ChkStart_LINMasterBaudrateViolation](Functions/CAPLfunctionChkStartLinMasterBaudrateViolation.md)
  - Checks the LIN Master baudrate.

- **LIN Configuration Requests**
  - [ChkStart_LINReconfRequestFormatViolation](Functions/CAPLfunctionChkStartLinReconfRequestFormatViolation.md)
  - Checks the format of LIN configuration requests.

- **LIN Diagnostic Delay Times**
  - [ChkStart_LINDiagDelayTimesViolation](Functions/CAPLfunctionChkStartLinDiagDelayTimesViolation.md)
  - Checks the values of P2_min and ST_min.

- **LIN Event Triggered Frame Format**
  - [ChkStart_LINETFViolation](Functions/CAPLfunctionChkStartLinEtfViolation.md)
  - Checks the format LIN Event-triggered frame response.

- **LIN Header Duration**
  - [ChkStart_LINHeaderToleranceViolation](Functions/CAPLfunctionChkStartLinHeaderToleranceViolation.md)
  - Checks the LIN header transmission time.

- **LIN Master Initialization Time**
  - [ChkStart_LINMasterInitTimeViolation](Functions/CAPLfunctionChkStartLinMasterInitTimeViolation.md)
  - Checks an initialization time of LIN Master.

- **LIN Response Error Flag**
  - [ChkStart_LINRespErrorSignal](Functions/CAPLfunctionChkStartLinRespErrorSignal.md)
  - Checks the LIN Response_Error signal.

- **LIN Schedule Table**
  - [ChkStart_LINSchedTableViolation](Functions/CAPLfunctionChkStartLinSchedTableViolation.md)
  - Checks LIN schedule table for correspondence with the database definition.

- **LIN Sync Break (Dominant Phase)**
  - [ChkStart_LINSyncBreakTimingViolation](Functions/CAPLfunctionChkStartLinSyncBreakTimingViolation.md)
  - Checks the timing of the synchronization break field (dominant phase) in LIN headers.

- **LIN Sync Break (Recessive Phase)**
  - [ChkStart_LINSyncDelTimingViolation](Functions/CAPLfunctionChkStartLinSyncDelTimingViolation.md)
  - Checks the timing of the synchronization break field (recessive phase) in LIN headers.

- **LIN Wake-up Request Length**
  - [ChkStart_LINWakeupReqLengthViolation](Functions/CAPLfunctionChkStartLinWakeupReqLengthViolation.md)
  - Checks the length of LIN Wakeup request.

- **LIN Wake-up Request Retries**
  - [ChkStart_LINWakeupRetryViolation](Functions/CAPLfunctionChkStartLinWakeupRetryViolation.md)
  - Checks number of LIN Wakeup requests and the time between them.

- **Message Count Observation** (FlexRay only)
  - [TestCheck::CreateMsgSendCountViolation, TestCheck::StartMsgSendCountViolation](Functions/CAPLfunctionTestCheckCreateMsgSendCountViolation.md)
  - [TestCheck::CreateNodeMsgSendCountViolation, TestCheck::StartNodeMsgSendCountViolation](Functions/CAPLfunctionTestCheckCreateMsgSendCountViolation.md)
  - Check is used to monitor the minimum and/or maximum number for each of the defined messages within a specified cyclic time interval.

- **Message Distance**
  - [ChkCreate_MsgDistViolation, ChkStart_MsgDistViolation](Functions/CAPLfunctionChkCreateMsgDistViolation.md)
  - This check is useful for spontaneous messages where one message depends to another message; e.g. for token-ring initializations for network management.

- **Messages Known**
  - [ChkCreate_UndefinedMessageReceived, ChkStart_UndefinedMessageReceived](Functions/CAPLfunctionChkCreateUndefinedMessageReceived.md)
  - This check listens to the bus and reports a violation, if a message was received that is not defined in any of the databases that are associated to the current bus.

- **MOST Error Messages**
  - [ChkCreate_MostErrorMessage, ChkStart_MostErrorMessage](Functions/CAPLfunctionChkCreateMostErrorMessage.md)
  - This check is used to monitor occurrence of MOST error messages.

- **MOST Light & Lock Observation**
  - [ChkCreate_MostCriticalUnlock, ChkStart_MostCriticalUnlock](Functions/CAPLfunctionChkCreateMostCriticalUnlock.md)
  - [ChkCreate_MostLightOff, ChkStart_MostLightOff](Functions/CAPLfunctionChkCreateMostLightOff.md)
  - [ChkCreate_MostShortUnlock, ChkStart_MostShortUnlock](Functions/CAPLfunctionChkCreateMostShortUnlock.md)
  - [ChkCreate_MostStableLock, ChkStart_MostStableLock](Functions/CAPLfunctionChkCreateMostStableLock.md)
  - This check is used to observe the Light & Lock condition of the MOST network interface.

- **MOST NetState Observation**
  - [ChkCreate_MostNetState, ChkStart_MostNetState](Functions/CAPLfunctionChkCreateMostNetState.md)
  - This check is used to monitor the NetState state of the MOST network interface.

- **MOST Property Protocol Observation**
  - [ChkCreate_MostPropertyProtocolError, ChkStart_MostPropertyProtocolError](Functions/CAPLfunctionChkCreateMostPropertyProtocolError.md)
  - This check observes the compliance to the MOST protocol with regard to message sequences and response times for a given property function.

- **MOST Method Protocol Observation**
  - [ChkCreate_MostMethodProtocolError, ChkStart_MostMethodProtocolError](Functions/CAPLfunctionChkCreateMostMethodProtocolError.md)
  - This check observes the compliance to the MOST protocol with regard to message sequences and response times for a given method function.

- **Node Active**
  - [ChkCreate_AllNodesDead, ChkStart_AllNodesDead](Functions/CAPLfunctionChkCreateAllNodesDead.md)
  - [ChkCreate_NodeDead, ChkStart_NodeDead](Functions/CAPLfunctionChkCreateNodeDead.md)
  - This check reports a problem, if the node has not send any of its Tx messages within a given time-interval.

- **Node Inactive**
  - [ChkCreate_AllNodesBabbling, ChkStart_AllNodesBabbling](Functions/CAPLfunctionChkCreateAllNodesBabbling.md)
  - [ChkCreate_NodeBabbling, ChkStart_NodeBabbling](Functions/CAPLfunctionChkCreateNodeBabbling.md)
  - This check allows the observation of the end of the activity of nodes.

- **No Value Change**
  - [ChkCreate_SignalValueChange, ChkStart_SignalValueChange](Functions/CAPLfunctionChkCreateSignalValueChange.md)
  - The check is useful to observe the constancy of a signal value.

- **OccurrenceCount**
  - [ChkCreate_MsgOccurrenceCount, ChkStart_MsgOccurrenceCount](Functions/CAPLfunctionChkCreateMsgOccurrenceCount.md)
  - [TestCheck::CreateNodeMsgsOccurrenceCount, TestCheck::StartNodeMsgsOccurrenceCount](Functions/CAPLfunctionChkCreateMsgOccurrenceCount.md)
  - The check is useful to observe the absence of defined messages on the bus.

- **Occurrence Distance**
  - [ChkCreate_NodeMsgsAbsDistViolation, ChkStart_ NodeMsgsAbsDistViolation](Functions/CAPLfunctionChkCreateNodeMsgsAbsDistViolation.md)
  - This check allows the supervision of the minimum send distance of all Tx messages of a node on one bus.

- **Occurrence of a Message**
  - [ChkCreate_MsgRelOccurrenceViolation, ChkStart_MsgRelOccurrenceViolation](Functions/CAPLfunctionChkCreateMsgRelOccurrenceViolation.md)
  - [ChkCreate_NodeMsgsRelOccurrenceViolation, ChkStart_NodeMsgsRelOccurrenceViolation](Functions/CAPLfunctionChkCreateNodeMsgsRelOccurrenceViolation.md)
  - Checks are used to monitor the sending delay of messages which allow both cyclic and spontaneous transmission.

- **Payload Gaps Observation**
  - [ChkCreate_PayloadGapsObservation, ChkStart_PayloadGapsObservation](Functions/CAPLfunctionChkCreatePayloadGapsObservation.md)
  - [ChkCreate_PayloadGapsObservationRx, ChkStart_PayloadGapsObservationRx](Functions/CAPLfunctionChkCreatePayloadGapsObservationRx.md)
  - [ChkCreate_PayloadGapsObservationTx, ChkStart_PayloadGapsObservationTx](Functions/CAPLfunctionChkCreatePayloadGapsObservationTx.md)
  - This check monitors the payload gaps and the DLC of a message.

- **Timeout**
  - [ChkCreate_Timeout, ChkStart_Timeout](Functions/CAPLfunctionChkCreateTimeout.md)
  - This checks creates an error event if particular time is expired.

- **Value Valid**
  - [ChkCreate_MsgSignalValueInvalid, ChkStart_MsgSignalValueInvalid](Functions/CAPLfunctionChkCreateMsgSignalValueInvalid.md)
  - [ChkCreate_MsgSignalValueRangeViolation, ChkStart_MsgSignalValueRangeViolation](Functions/CAPLfunctionChkCreateMsgSignalValueRangeViolation.md)
  - This check is useful to supervise the value of signals.

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
