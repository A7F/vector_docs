[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssWaitForStoreConfReq.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsLssWaitForStoreConfigurationRequest

# coTfsLssWaitForStoreConfigurationRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForStoreConfigurationRequest( dword errorCode, dword specificError );
```

## Description

This function waits for the **LSS store configuration** request and sends the response.

## Parameters

- **errorCode**  
  Error code.  
  - 0 - protocol successfully completed
  - 1 - store configuration not supported
  - 2 - storage media access error
  - 255 - implementation specific error occurred

- **specificError**  
  Manufacturer specific error (used if error code = 255).

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* waits for LSS store configuration request */
if (coTfsLssWaitForStoreConfigurationRequest( 0, 0) == 1) {
  /* received LSS store configuration request, sent response with error code and specific error = 0 */
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)