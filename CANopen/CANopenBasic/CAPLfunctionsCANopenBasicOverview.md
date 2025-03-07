# CANopen Basic Functions

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/CAPLfunctionsCANopenBasicOverview.md)

**CAPL Functions** » [CANopen](../CAPLfunctionsCANopenOverview.md) » Basic Functions

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

This section offers an overview of the CANopen basic CAPL functions.

## Functions and Descriptions

- [CANopenDomainServerOpenFileRead](Functions/CAPLfunctionsCANopenDomainServerOpenFileRead.md): Opens the file for a domain data object of a CANopen node for read access.
- [CANopenDomainServerSetFileContents](Functions/CAPLfunctionsCANopenDomainServerSetFileContents.md): Sets the contents of a domain data object file of a CANopen node.
- [CANopenDownload](Functions/CAPLfunctionsCANopenDownload.md): Writes an entry in the object dictionary of another node using the SDO protocol.
- [CANopenDownloadDomain](Functions/CAPLfunctionsCANopenDownloadDomain.md): Writes an entry of type DOMAIN in the object dictionary of another node.
- [CANopenDownloadDomainFromFile](Functions/CAPLfunctionsCANopenDownloadDomainFromFile.md): Writes the contents of a file to an entry of type DOMAIN in the object dictionary of another node.
- [CANopenEmergency](Functions/CAPLfunctionsCANopenEmergency.md): Activates/deactivates an emergency error code.
- [CANopenInternalNMTCommand](Functions/CAPLfunctionsCANopenInternalNMTCommand.md): Performs an NMT command inside a simulated CANopen node.
- [CANopenLssActivateBitTimingParameters](Functions/CAPLfunctionsCANopenLssActivateBitTimingParameters.md): The LSS master activates the bit timing of a LSS slave.
- [CANopenLssConfigNodeId](Functions/CAPLfunctionsCANopenLssConfigNodeId.md): The LSS master configures the node ID of a LSS slave.
- [CANopenLssConfigureBitTimingParameters](Functions/CAPLfunctionsCANopenLssConfigureBitTimingParameters.md): The LSS master configures the bit timing of a LSS slave.
- [CANopenLssFastScan](Functions/CAPLfunctionsCANopenLssFastScan.md): The LSS master start a LSS fast scan to identify and unconfigured LSS slave.
- [CANopenLssIdentNonConfigSlave](Functions/CAPLfunctionsCANopenLssIdentNonConfigSlave.md): The LSS master commands all LSS slaves without configured node-ID to identify themselves.
- [CANopenLssIdentRemoteSlave](Functions/CAPLfunctionsCANopenLssIdentRemoteSlave.md): The LSS master commands all LSS slaves whose LSS address matches the transmitted LSS address parameters to identify themselves.
- [CANopenLssInqNodeId](Functions/CAPLfunctionsCANopenLssInqNodeId.md): Requests the node ID of a LSS slave.
- [CANopenLssInqProdCode](Functions/CAPLfunctionsCANopenLssInqProdCode.md): Requests the product code of a LSS slave.
- [CANopenLssInqRevNo](Functions/CAPLfunctionsCANopenLssInqRevNo.md): Requests the revision number of a LSS slave.
- [CANopenLssInqSerialNo](Functions/CAPLfunctionsCANopenLssInqSerialNo.md): Requests the serial number of a LSS slave.
- [CANopenLssInqVendorId](Functions/CAPLfunctionsCANopenLssInqVendorId.md): Requests the vendor ID of a LSS slave.
- [CANopenLssStoreConfig](Functions/CAPLfunctionsCANopenLssStoreConfig.md): The configured parameters are written into nonvolatile memory of a LSS slave.
- [CANopenLssSwitchModeGlob](Functions/CAPLfunctionsCANopenLssSwitchModeGlob.md): Sets LSS slaves to the configuration mode or leave the mode.
- [CANopenLssSwitchModeSel](Functions/CAPLfunctionsCANopenLssSwitchModeSel.md): Sets LSS slaves to the configuration mode or leave the mode.
- [CANopenTriggerTPDO](Functions/CAPLfunctionsCANopenTriggerTPDO.md): Triggers the immediate transmission of a TPDO.
- [CANopenUpload](Functions/CAPLfunctionsCANopenUpload.md): Reads an entry from the object dictionary of another node using the SDO protocol.
- [CANopenUploadAll](Functions/CAPLfunctionsCANopenUploadAll.md): Reads all objects from the object dictionary of another node.
- [CANopenUploadDomain](Functions/CAPLfunctionsCANopenUploadDomain.md): Reads an entry of type DOMAIN from the object dictionary of another node.
- [CANopenUploadGetData](Functions/CAPLfunctionsCANopenUploadGetData.md): Returns the data of a CANopen upload in a callback function as char or byte array.
- [CANopenUploadGetDouble](Functions/CAPLfunctionsCANopenUploadGetDouble.md): Returns the data of a CANopen upload in a callback function as double.
- [CANopenUploadGetSigned](Functions/CAPLfunctionsCANopenUploadGetSigned.md): Returns the data of a CANopen upload in a callback function as a signed value.
- [CANopenUploadGetUnsigned](Functions/CAPLfunctionsCANopenUploadGetUnsigned.md): Returns the data of a CANopen upload in a callback function as an unsigned value.

## Test Feature Set for CANopen

- [TestDisableMsg](../../Test/Functions/CAPLfunctionTestDisableMsg.md): Prevents all sending of the message except the sending by calling the function [testSetMsgEvent](../../Test/Functions/CAPLfunctionTestSetMsgEvent.md).
- [TestEnableMsg](../../Test/Functions/CAPLfunctionTestEnableMsg.md): Enables the sending of the message.
- [TestDisableMsgAllTx](../../Test/Functions/CAPLfunctionTestDisableMsgAllTx.md): Prevents all sending of tx messages of the node except the sending with [testSetMsgEvent](../../Test/Functions/CAPLfunctionTestSetMsgEvent.md).
- [TestEnableMsgAllTx](../../Test/Functions/CAPLfunctionTestEnableMsgAllTx.md): Enables the sending of all tx messages of a node.
- [TestSetMsgCycleTime](../../Test/Functions/CAPLfunctionTestSetMsgCycleTime.md): Assigns a new cycle time to the message.
- [TestResetMsgCycleTime](../../Test/Functions/CAPLfunctionTestResetMsgCycleTime.md): Resets the cycle time of the message to the database cycle time.
- [TestSetMsgEvent](../../Test/Functions/CAPLfunctionTestSetMsgEvent.md): Sends the message once.
- [TestSetMsgDlc](../../Test/Functions/CAPLfunctionTestSetSetMsgDlc.md): Assigns a new DLC to the message.
- [TestResetAllFaultInjections](../../Test/Functions/CAPLfunctionTestResetAllFaultInjections.md): Reset all fault injection settings.

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)