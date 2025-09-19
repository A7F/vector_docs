[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/CAPLfunctionsXCPOverview.md)

## XCP CAPL Functions

[CAPL Functions](../CAPLfunctions.md) » XCP CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**XCP**  
Only available with Option AMD/XCP.  
The functions can be used for XCP and CCP devices.

### Functions

- [OnXcpConnect](Functions/CAPLfunctionXCPConnect.md)  
  Is called after establishing the connection with [xcpConnect](Functions/CAPLfunctionXCPConnect.md) and before start of the DAQ measurement.

- [OnXcpDisconnect](Functions/CAPLfunctionXCPDisconnect.md)  
  Is called after the ECU acknowledged the disconnect command.

- [OnXcpError](Functions/CAPLfunctionOnXcpError.md)  
  Is called whenever the XCP slaves answers with a negative response.

- [OnXcpEvent](Functions/CAPLfunctionOnXcpEvent.md)  
  Provides access to data that is sent from an XCP or CCP slave in an Event packet.

- [OnXcpGetCalPage](Functions/CAPLfunctionXCPGetCalPage.md)  
  Is called to get the currently active calibration data page of an ECU.

- [OnXcpSendRaw](Functions/CAPLfunctionXCPSendRaw.md)  
  Is called with the response to a raw XCP command sent by [xcpSendRaw](Functions/CAPLfunctionXCPSendRaw.md).

- [OnXcpSetCalPage](Functions/CAPLfunctionXCPSetCalPage.md)  
  Is called when the ECU switched the calibration data page.

- [OnXcpUpload](Functions/CAPLfunctionXCPUpload.md)  
  Is called after finishing of the upload with [xcpUpload](Functions/CAPLfunctionXCPUpload.md) to indicate the upload status.

- [OnXcpUserCommand](Functions/CAPLfunctionXCPUserCommand.md)  
  Is called for a response of a user command.

- [xcpActivate](Functions/CAPLfunctionXCPActivate.md)  
  Activates an a2l parameter for upload and DAQ measurement.

- [xcpActivateMeasurementGroup](Functions/CAPLfunctionXCPActivateMeasurementGroup.md)  
  Changes the measurement group that will be used for the next connection to the XCP/CCP device.

- [xcpConnect](Functions/CAPLfunctionXCPConnect.md)  
  Establishes a connection to the XCP/CCP device and starts the configured DAQ measurement.

- [xcpDeactivate](Functions/CAPLfunctionXCPDeactivate.md)  
  Upload and DAQ measurement will be deactivated.

- [xcpDeactivateAll](Functions/CAPLfunctionXCPDeactivateAll.md)  
  Deactivates **auto read** of all configured parameters of the active measurement group.

- [xcpDisconnect](Functions/CAPLfunctionXCPDisconnect.md)  
  Disconnects from a XCP/CCP device.

- [xcpGetCalPage](Functions/CAPLfunctionXCPGetCalPage.md)  
  If the XCP slave device supports calibration data page switching, this command gets the currently active page and access mode.

- [xcpGetPollingCycle](Functions/CAPLfunctionXCPGetPollingCycle.md)  
  Returns the cycle time of a parameter, if the read mode of the parameter is set to **polling**.

- [xcpIsConnected](Functions/CAPLfunctionXCPIsConnected.md)  
  Returns the connection status of a XCP/CCP device.

- [xcpSendRaw](Functions/CAPLfunctionXCPSendRaw.md)  
  Sends any data as control command to an XCP/CCP device.

- [xcpSetCalPage](Functions/CAPLfunctionXCPSetCalPage.md)  
  If the XCP slave device supports calibration data page switching, this command sets the current page and access mode.

- [xcpSetPollingCycle](Functions/CAPLfunctionXCPSetPollingCycle.md)  
  Sets the cycle time of a parameter, if the read mode of the parameter is set to **polling**.

- [xcpUpload](Functions/CAPLfunctionXCPUpload.md)  
  Upload of the parameter and update of the system variable.

- [xcpUserCommand](Functions/CAPLfunctionXCPUserCommand.md)  
  Sends user-defined data to the XCP slave.

[Option .AMD/XCP](../../CANoeCANalyzer/AMDXCP/AMDXCP.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
