[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoAbort.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsSDOAbort**

# coTfsSDOAbort (Level 1)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

```plaintext
long coTfsSDOAbort( dword index, dword subIndex, dword abortCode );
```

## Description

This function sends out a SDO abort message.

## Parameters

- **index**: Object index
- **subIndex**: Object subindex
- **abortCode**: Abort code

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
long retValFunc = kTestStepPassed; /* to store the return value of function */
long nodeId = 112; /* Node-Id of DUT */

dword index = 0x1017; /* object index */
dword subIndex = 0; /* object sub-index */
dword ccs = kClientCommandSpecifier_InitiateDownloadRequest;
dword expedited = kTransfer_Normal;
dword sizeIndicated = kSize_Indicated;
dword notUsed = 0; /* no of byte without data */
byte inValueBuf[4] = {0x2, 0x0, 0x0, 0x0}; /* length of data to be downloaded */
dword valueBufSize = 4;
dword abortCode = 0;
char msg[100];
retValFunc = kTestStepPassed;
msg[0] = '\0';

/* Set the node-ID of DUT */
strncpy(msg,"Set node-ID", elCount(msg));
retValFunc = coTfsSetNodeId(nodeId);

/* initiate download request */
if (retValFunc == kTestStepPassed)
{
  strncpy(msg,"coTfsSDOInit", elCount(msg));
  ccs = kClientCommandSpecifier_InitiateDownloadRequest;
  expedited = kTransfer_Normal;
  sizeIndicated = kSize_Indicated;
  notUsed = 3; /* number of bytes does not contains data bytes */
  inValueBuf[0] = 0x2;
  inValueBuf[1] = 0x0;
  inValueBuf[2] = 0x0;
  inValueBuf[3] = 0x0;
  retValFunc = coTfsSDOInit( index /*dword index*/, subIndex /*dword subIndex*/, ccs /*dword ccs*/, expedited /*dword expedited*/, sizeIndicated /*dword sizeIndicated*/, notUsed /*dword notUsed*/, inValueBuf /*byte inValueBuf[]*/, valueBufSize /*dword valueBufSize*/ );
} /* if */

/* download segment request */
if (retValFunc == kTestStepPassed)
{
  strncpy(msg,"coTfsSDOAbort", elCount(msg));
  abortCode = 0x08000000; /* general error */
  retValFunc = coTfsSDOAbort( index /*dword index*/, subIndex /*dword subIndex*/, abortCode /*dword abortCode*/ );
} /* if */

/* evaluation of returned value */
if (retValFunc != kTestStepPassed)
{
  /* outputs a failure message to the Write Window */
  write("%s failed", msg);
  /* Set testfunction or test case as failed; The message will be appeared in report if it is enabled */
  /* testStepFail( "CAPL text", "%s failed", msg); */
} /* if */
```

[Used Constants](../CAPLfunctionsCANopenNLTFSExampleConstants.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)