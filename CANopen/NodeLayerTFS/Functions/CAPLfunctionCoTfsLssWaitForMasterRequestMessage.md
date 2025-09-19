# coTfsLssWaitForMasterRequestMessage (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForMasterRequestMessage( void );
```

## Description

This function waits for one of the LSS Master requests which have been configured before. Depending on the request, an appropriate response is sent.

If several requests occur during the wait process, all requests are handled. After a single event the function waits for a further event (standard timeout) if at least one wait condition is available. So the whole wait time of the function can exceed the standard timeout.

To configure LSS Master requests, you can use the following functions:

- [coTfsLssAddMasterResponseActivateBitTiming](CAPLfunctionCoTfsLssAddMasterResponseActivateBitTiming.md)
- [coTfsLssAddMasterResponseConfigureBitTiming](CAPLfunctionCoTfsLssAddMasterResponseConfigureBitTiming.md)
- [coTfsLssAddMasterResponseConfigureNodeId](CAPLfunctionCoTfsLssAddMasterResponseConfigureNodeId.md)
- [coTfsLssAddMasterResponseIdentifyFastscan](CAPLfunctionCoTfsLssAddMasterResponseIdentifyFastscan.md)
- [coTfsLssAddMasterResponseIdentifyNonConfRemoteSlv](CAPLfunctionCoTfsLssAddMasterResponseIdentifyNonConfRemoteSlv.md)
- [coTfsLssAddMasterResponseIdentifyRemoteSlave](CAPLfunctionCoTfsLssAddMasterResponseIdentifyRemoteSlave.md)
- [coTfsLssAddMasterResponseInquireNodeId](CAPLfunctionCoTfsLssAddMasterResponseInquireNodeId.md)
- [coTfsLssAddMasterResponseInquireProductCode](CAPLfunctionCoTfsLssAddMasterResponseInquireProductCode.md)
- [coTfsLssAddMasterResponseInquireRevisionNo](CAPLfunctionCoTfsLssAddMasterResponseInquireRevisionNo.md)
- [coTfsLssAddMasterResponseInquireSerialNo](CAPLfunctionCoTfsLssAddMasterResponseInquireSerialNo.md)
- [coTfsLssAddMasterResponseInquireVendorId](CAPLfunctionCoTfsLssAddMasterResponseInquireVendorId.md)
- [coTfsLssAddMasterResponseStoreConfiguration](CAPLfunctionCoTfsLssAddMasterResponseStoreConfiguration.md)
- [coTfsLssAddMasterResponseSwitchStateGlobal](CAPLfunctionCoTfsLssAddMasterResponseSwitchStateGlobal.md)
- [coTfsLssAddMasterResponseSwitchStateSelective](CAPLfunctionCoTfsLssAddMasterResponseSwitchStateSelective.md)

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)
