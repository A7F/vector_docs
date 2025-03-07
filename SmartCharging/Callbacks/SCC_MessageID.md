[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/SCC_MessageID.md)

## CAPL Functions » Smart Charging » Message ID

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » Message ID

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Note

- The available Message IDs depend on the protocol(s) used and thus the underlying technology.

### CCS-Binding

The following table applies to all callbacks and functions where a message ID is included.

- **SLAC**
  - CM_SLAC_PARM: Req (1), Cnf (2)
  - CM_START_ATTEN_CHAR: Ind (3), — (—)
  - CM_MNBC_SOUND: Ind (4), — (—)
  - CM_ATTEN_CHAR: Ind (5), Rsp (6)
  - CM_ATTEN_PROFILE: Ind (7), — (—)
  - CM_VALIDATE: Req (8), Cnf (9)
  - CM_SLAC_MATCH: Req (10), Cnf (11)
  - CM_SET_KEY: Req (12), Cnf (13)
  - CM_AMP_MAP: Req (14), Cnf (15)
  - VS_HOST_ACTION: Ind (16), — (—)

- **SECC Discovery**
  - SECCDiscovery: Req (50), Res (51)
  - SECCDiscoveryWireless: Req (52), Res (53)

- **Supported App Protocol**
  - SupportedAppProtocol: Req (80), Res (81)

- **DIN 70121**
  - SessionSetup: Req (100), Res (101)
  - ServiceDiscovery: Req (102), Res (103)
  - ServicePaymentSelection: Req (104), Res (105)
  - ContractAuthentication: Req (106), Res (107)
  - ChargeParameterDiscovery: Req (108), Res (109)
  - PowerDelivery: Req (110), Res (111)
  - SessionStop: Req (112), Res (113)
  - CableCheck: Req (114), Res (115)
  - PreCharge: Req (116), Res (117)
  - CurrentDemand: Req (118), Res (119)
  - WeldingDetection: Req (120), Res (121)

- **ISO2 CM**
  - SessionSetup: Req (200), Res (201)
  - ServiceDiscovery: Req (202), Res (203)
  - ServiceDetail: Req (204), Res (205)
  - PaymentServiceSelection: Req (206), Res (207)
  - PaymentDetails: Req (208), Res (209)
  - Authorization: Req (210), Res (211)
  - ChargeParameterDiscovery: Req (212), Res (213)
  - PowerDelivery: Req (214), Res (215)
  - MeteringReceipt: Req (216), Res (217)
  - SessionStop: Req (218), Res (219)
  - CertificateUpdate: Req (220), Res (221)
  - CertificateInstallation: Req (222), Res (223)

- **ISO2 AC**
  - ChargingStatus: Req (224), Res (225)

- **ISO2 DC**
  - CableCheck: Req (226), Res (227)
  - PreCharge: Req (228), Res (229)
  - CurrentDemand: Req (230), Res (231)
  - WeldingDetection: Req (232), Res (233)

- **ISO20 CM**
  - SessionSetup: Req (300), Res (301)
  - AuthorizationSetup: Req (302), Res (303)
  - Authorization: Req (304), Res (305)
  - ServiceDiscovery: Req (306), Res (307)
  - ServiceDetail: Req (308), Res (309)
  - ServiceSelection: Req (310), Res (311)
  - ScheduleExchange: Req (312), Res (313)
  - PowerDelivery: Req (314), Res (315)
  - SessionStop: Req (318), Res (319)
  - CertificateInstallation: Req (320), Res (321)
  - VehicleCheckIn: Req (322), Res (323)
  - VehicleCheckOut: Req (324), Res (325)

- **ISO20 AC**
  - ACChargeParameterDiscovery: Req (326), Res (327)
  - ACChargeLoop: Req (328), Res (329)

- **ISO20 DC**
  - DCChargeParameterDiscovery: Req (330), Res (331)
  - DCCableCheck: Req (332), Res (333)
  - DCPreCharge: Req (334), Res (335)
  - DCChargeLoop: Req (336), Res (337)
  - DCWeldingDetection: Req (338), Res (339)

- **ISO20 WPT**
  - WPTFinePositioningSetup: Req (348), Res (349)
  - WPTFinePositioning: Req (350), Res (351)
  - WPTPairingReq: Req (352), Res (353)
  - WPTChargeParameterDiscovery: Req (354), Res (355)
  - WPTAlignmentCheck: Req (356), Res (357)
  - WPTChargeLoop: Req (358), Res (359)

- **ScheduleRenegotiation**
  - SRACChargeParameterDiscovery: Req (400), Res (401)
  - SRDCChargeParameterDiscovery: Req (402), Res (403)
  - SRScheduleExchange: Req (404), Res (405)
  - SRPowerDelivery: Req (406), Res (407)
  - SRWPTChargeParameterDiscovery: Req (408), Res (409)

- **MeteringConfirmation**
  - MeteringConfirmation: Req (450), Res (451)

- **Vendor MME**
  - VS_GET_PWM_STATS: Ind (1404), — (—)
  - VS_GET_STATUS: Req (1411), Cnf (1412)
  - VS_GET_VERSION: Req (1415), Cnf (1416)
  - VS_GET_PWM_CONF: Req (1420), Cnf (1421)
  - VS_SET_PWM_CONF: Req (1425), Cnf (1426)

- **Lumissil MME**
  - Lumissil_GET_VERSION: Req (1500), Cnf (1501)
  - Lumissil_D_Link_Status: Req (1502), Cnf (1503)
  - Lumissil_Host_Message: Ind (1504), — (—)

### Modeling Libraries

The following table applies to all callback functions where a message ID is included.

- **Vendor/Hardware**
  - Invalid message: — (0), — (—)
  - SECCDiscovery: Req (1), Res (2)
  - SupportedAppProtocol: Req (3), Res (4)
  - SessionSetup: Req (5), Res (6)
  - ServiceDiscovery: Req (7), Res (8)
  - ServiceDetail: Req (9), Res (10)
  - PaymentServiceSelection: Req (11), Res (12)
  - PaymentDetails: Req (13), Res (14)
  - Authorization: Req (15), Res (16)
  - ChargeParameterDiscovery: Req (17), Res (18)
  - PowerDelivery: Req (19), Res (20)
  - ChargingStatus: Req (21), Res (22)
  - MeteringReceipt: Req (23), Res (24)
  - CableCheck: Req (25), Res (26)
  - PreCharge: Req (27), Res (28)
  - CurrentDemand: Req (29), Res (30)
  - WeldingDetection: Req (31), Res (32)
  - SessionStop: Req (33), Res (34)
  - CertificateUpdate: Req (35), Res (36)
  - CertificateInstallation: Req (37), Res (38)
  - CmSLACParm: Req (101), Cnf (102)
  - CmStartAttenChar: Ind (103), — (—)
  - CmMNBCSound: Ind (105), — (—)
  - CmAttenProfile: Ind (107), — (—)
  - VsAttenChar: — (109), — (—)
  - CmAttenChar: Ind (111), Rsp (112)
  - CmValidate: Req (113), Cnf (114)
  - CmSLACMatch: Req (115), Cnd (116)
  - CmSetKey: Req (117), Cnf (118)
  - VsSetKey: Req (119), Cnf (120)
  - CmAmpMap: Req (121), Cnf (122)
  - VsPlLnkStatus: Req (123), Cnf (124)
  - StLinkStatus: Req (125), Cnf (126)
  - VsNwInfo: Req (127), Cnf (128)
  - UnassociatedSta: Ind (201), — (—)
  - CcAssoc: Req (203), Cnf (204)
  - CcSetTeiMap: Ind (205), — (—)
  - CmEncryptedPayload: Ind (207), — (—)
  - CmStaIndentify: Ind (209), Rsp (210)
  - CmBridgeInfo: Req (211), Cnf (212)
  - CcLinkInfo: Ind (213), Rsp (214)
  - CmHFID: Req (215), Cnf (216)
  - VsGetPWMStats: Req (217), Cnf (218)
  - VsGetPWMStats: Ind (219), — (—)
  - VsGetPWMConf: Req (221), Cnf (222)
  - VsSetPWMConf: Req (223), Cnf (224)
  - VsGetStatus: Req (225), Cnf (226)
  - VsGetEthPhy: Req (301), Cnf (302)
  - VsGetNwInfo: Req (303), Cnf (304)
  - VsEthStats: Req (305), Cnf (306)
  - VsGetVersion: Req (307), Cnf (308)
  - VsReset: Req (309), Cnf (310)

### Vehicle States

The following table applies to [SCC_StateTransitionInd](CAPLfunctionSCCStateTransitionInd.md) of the vehicle simulation.

- **General States**
  - Initial: 0
  - Error: 200

- **Message related states**
  - Session Setup: 1
  - Service Discovery: 2
  - Service Details: 3
  - Service / Payment Selection: 4
  - Payment Details: 5
  - Authentication / Authorization: 6
  - Charge Parameter Discovery: 7
  - Power Delivery: 8
  - Charging Status: 9
  - Metering Receipt: 10
  - Cable Check: 11
  - PreCharge: 12
  - Current Demand: 13
  - Welding Detection: 14
  - Session Stop: 15
  - CertificateUpdate: 16
  - CertificateInstallation: 17

### Charge Point States

The following table applies to [SCC_StateTransitionInd](CAPLfunctionSCCStateTransitionInd.md) of the charge point simulation.

- **General States**
  - Initial: 0
  - Error: 200
  - Waiting for new session: 201
  - Reconnecting: 300

- **Message related states**
  - Session Setup: 1
  - Service Discovery: 2
  - Service / Payment Selection: 3
  - Payment Details: 4
  - Payment Details / Certificate transfer: 5
  - Authentication / Authorization: 6
  - Charge Parameter Discovery: 7
  - Power Delivery: 8
  - Charging Status: 9
  - Metering Receipt: 10
  - Cable Check: 11
  - PreCharge: 12
  - Current Demand: 13
  - Welding Detection: 14
  - Welding Detection or Renegotiation: 15
  - Renegotiation: 16
  - Session Stop: 17
  - Session Stop or Renegotiation: 18

### OCCP-Binding

The following table applies to all callbacks and functions where a message ID is included.

- **General**
  - Undefined: 0
  - ErrorResponse: 50

- **OCPP 1.6**
  - AuthorizeRequest_16: 100
  - AuthorizeResponse_16: 101
  - BootNotificationRequest_16: 102
  - BootNotificationResponse_16: 103
  - CancelReservationRequest_16: 104
  - CancelReservationResponse_16: 105
  - CertificateSignedRequest_16: 106
  - CertificateSignedResponse_16: 107
  - ChangeAvailabilityRequest_16: 108
  - ChangeAvailabilityResponse_16: 109
  - ChangeConfigurationRequest_16: 110
  - ChangeConfigurationResponse_16: 111
  - ClearCacheRequest_16: 112
  - ClearCacheResponse_16: 113
  - ClearChargingProfileRequest_16: 114
  - ClearChargingProfileResponse_16: 115
  - DataTransferRequest_16: 116
  - DataTransferResponse_16: 117
  - DeleteCertificateRequest_16: 118
  - DeleteCertificateResponse_16: 119
  - DiagnosticsStatusNotificationRequest_16: 120
  - DiagnosticsStatusNotificationResponse_16: 121
  - ExtendedTriggerMessageRequest_16: 122
  - ExtendedTriggerMessageResponse_16: 123
  - FirmwareStatusNotificationRequest_16: 124
  - FirmwareStatusNotificationResponse_16: 125
  - GetCompositeScheduleRequest_16: 126
  - GetCompositeScheduleResponse_16: 127
  - GetConfigurationRequest_16: 128
  - GetConfigurationResponse_16: 129
  - GetDiagnosticsRequest_16: 130
  - GetDiagnosticsResponse_16: 131
  - GetInstalledCertificateIdsRequest_16: 132
  - GetInstalledCertificateIdsResponse_16: 133
  - GetLocalListVersionRequest_16: 134
  - GetLocalListVersionResponse_16: 135
  - GetLogRequest_16: 136
  - GetLogResponse_16: 137
  - HeartbeatRequest_16: 138
  - HeartbeatResponse_16: 139
  - InstallCertificateRequest_16: 140
  - InstallCertificateResponse_16: 141
  - LogStatusNotificationRequest_16: 142
  - LogStatusNotificationResponse_16: 143
  - MeterValuesRequest_16: 144
  - MeterValuesResponse_16: 145
  - RemoteStartTransactionRequest_16: 146
  - RemoteStartTransactionResponse_16: 147
  - RemoteStopTransactionRequest_16: 148
  - RemoteStopTransactionResponse_16: 149
  - ReserveNowRequest_16: 150
  - ReserveNowResponse_16: 151
  - ResetRequest_16: 152
  - ResetResponse_16: 153
  - SecurityEventNotificationRequest_16: 154
  - SecurityEventNotificationResponse_16: 155
  - SendLocalListRequest_16: 156
  - SendLocalListResponse_16: 157
  - SignedFirmwareStatusNotificationRequest_16: 158
  - SignedFirmwareStatusNotificationResponse_16: 159
  - SetChargingProfileRequest_16: 160
  - SetChargingProfileResponse_16: 161
  - SignedUpdateFirmwareRequest_16: 162
  - SignedUpdateFirmwareResponse_16: 163
  - SignCertificateRequest_16: 164
  - SignCertificateResponse_16: 165
  - StartTransactionRequest_16: 166
  - StartTransactionResponse_16: 167
  - StatusNotificationRequest_16: 168
  - StatusNotificationResponse_16: 169
  - StopTransactionRequest_16: 170
  - StopTransactionResponse_16: 171
  - TriggerMessageRequest_16: 172
  - TriggerMessageResponse_16: 173
  - UnlockConnectorRequest_16: 174
  - UnlockConnectorResponse_16: 175
  - UpdateFirmwareRequest_16: 176
  - UpdateFirmwareResponse_16: 177

- **OCPP 2.0.1**
  - AuthorizeRequest_201: 200
  - AuthorizeResponse_201: 201
  - BootNotificationRequest_201: 202
  - BootNotificationResponse_201: 203
  - CancelReservationRequest_201: 204
  - CancelReservationResponse_201: 205
  - CertificateSignedRequest_201: 206
  - CertificateSignedResponse_201: 207
  - ChangeAvailabilityRequest_201: 208
  - ChangeAvailabilityResponse_201: 209
  - ClearCacheRequest_201: 210
  - ClearCacheResponse_201: 211
  - ClearChargingProfileRequest_201: 212
  - ClearChargingProfileResponse_201: 213
  - ClearDisplayMessageRequest_201: 214
  - ClearDisplayMessageResponse_201: 215
  - ClearedChargingLimitRequest_201: 216
  - ClearedChargingLimitResponse_201: 217
  - ClearVariableMonitoringRequest_201: 218
  - ClearVariableMonitoringResponse_201: 219
  - CostUpdatedRequest_201: 220
  - CostUpdatedResponse_201: 221
  - CustomerInformationRequest_201: 222
  - CustomerInformationResponse_201: 223
  - DataTransferRequest_201: 224
  - DataTransferResponse_201: 225
  - DeleteCertificateRequest_201: 226
  - DeleteCertificateResponse_201: 227
  - FirmwareStatusNotificationRequest_201: 228
  - FirmwareStatusNotificationResponse_201: 229
  - Get15118EVCertificateRequest_201: 230
  - Get15118EVCertificateResponse_201: 231
  - GetBaseReportRequest_201: 232
  - GetBaseReportResponse_201: 233
  - GetCertificateStatusRequest_201: 234
  - GetCertificateStatusResponse_201: 235
  - GetChargingProfilesRequest_201: 236
  - GetChargingProfilesResponse_201: 237
  - GetCompositeScheduleRequest_201: 238
  - GetCompositeScheduleResponse_201: 239
  - GetDisplayMessagesRequest_201: 240
  - GetDisplayMessagesResponse_201: 241
  - GetInstalledCertificateIdsRequest_201: 242
  - GetInstalledCertificateIdsResponse_201: 243
  - GetLocalListVersionRequest_201: 244
  - GetLocalListVersionResponse_201: 245
  - GetLogRequest_201: 246
  - GetLogResponse_201: 247
  - GetMonitoringReportRequest_201: 248
  - GetMonitoringReportResponse_201: 249
  - GetReportRequest_201: 250
  - GetReportResponse_201: 251
  - GetTransactionStatusRequest_201: 252
  - GetTransactionStatusResponse_201: 253
  - GetVariablesRequest_201: 254
  - GetVariablesResponse_201: 255
  - HeartbeatRequest_201: 256
  - HeartbeatResponse_201: 257
  - InstallCertificateRequest_201: 258
  - InstallCertificateResponse_201: 259
  - LogStatusNotificationRequest_201: 260
  - LogStatusNotificationResponse_201: 261
  - MeterValuesRequest_201: 262
  - MeterValuesResponse_201: 263
  - NotifyChargingLimitRequest_201: 264
  - NotifyChargingLimitResponse_201: 265
  - NotifyCustomerInformationRequest_201: 266
  - NotifyCustomerInformationResponse_201: 267
  - NotifyDisplayMessagesRequest_201: 268
  - NotifyDisplayMessagesResponse_201: 269
  - NotifyEVChargingNeedsRequest_201: 270
  - NotifyEVChargingNeedsResponse_201: 271
  - NotifyEVChargingScheduleRequest_201: 272
  - NotifyEVChargingScheduleResponse_201: 273
  - NotifyEventRequest_201: 274
  - NotifyEventResponse_201: 275
  - NotifyMonitoringReportRequest_201: 276
  - NotifyMonitoringReportResponse_201: 277
  - NotifyReportRequest_201: 278
  - NotifyReportResponse_201: 279
  - PublishFirmwareRequest_201: 280
  - PublishFirmwareResponse_201: 281
  - PublishFirmwareStatusNotificationRequest_201: 282
  - PublishFirmwareStatusNotificationResponse_201: 283
  - ReportChargingProfilesRequest_201: 284
  - ReportChargingProfilesResponse_201: 285
  - RequestStartTransactionRequest_201: 286
  - RequestStartTransactionResponse_201: 287
  - RequestStopTransactionRequest_201: 288
  - RequestStopTransactionResponse_201: 289
  - ReservationStatusUpdateRequest_201: 290
  - ReservationStatusUpdateResponse_201: 291
  - ReserveNowRequest_201: 292
  - ReserveNowResponse_201: 293
  - ResetRequest_201: 294
  - ResetResponse_201: 295
  - SecurityEventNotificationRequest_201: 296
  - SecurityEventNotificationResponse_201: 297
  - SendLocalListRequest_201: 298
  - SendLocalListResponse_201: 299
  - SetChargingProfileRequest_201: 300
  - SetChargingProfileResponse_201: 301
  - SetDisplayMessageRequest_201: 302
  - SetDisplayMessageResponse_201: 303
  - SetMonitoringBaseRequest_201: 304
  - SetMonitoringBaseResponse_201: 305
  - SetMonitoringLevelRequest_201: 306
  - SetMonitoringLevelResponse_201: 307
  - SetNetworkProfileRequest_201: 308
  - SetNetworkProfileResponse_201: 309
  - SetVariableMonitoringRequest_201: 310
  - SetVariableMonitoringResponse_201: 311
  - SetVariablesRequest_201: 312
  - SetVariablesResponse_201: 313
  - SignCertificateRequest_201: 314
  - SignCertificateResponse_201: 315
  - StatusNotificationRequest_201: 316
  - StatusNotificationResponse_201: 317
  - TransactionEventRequest_201: 318
  - TransactionEventResponse_201: 319
  - TriggerMessageRequest_201: 320
  - TriggerMessageResponse_201: 321
  - UnlockConnectorRequest_201: 322
  - UnlockConnectorResponse_201: 323
  - UnpublishFirmwareRequest_201: 324
  - UnpublishFirmwareResponse_201: 325
  - UpdateFirmwareRequest_201: 326
  - UpdateFirmwareResponse_201: 327

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)