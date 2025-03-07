[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsOdChkSingleEntryNotExist.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsODChkSingleEntryNotExist**

# coTfsODChkSingleEntryNotExist (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

```plaintext
long coTfsODChkSingleEntryNotExist( dword index, dword subIndex );
```

## Description

The function checks with a SDO upload if the given object does not exist in the object dictionary. The device must answer with one of these SDO abort codes: 0x08000000, 0x06020000 or 0x06090011.

If the entry exists and the subindex is 0, the functions checks automatically the subindexes 1..255.

## Parameters

- **index**: Object index
- **subIndex**: Object subindex

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
long retValFunc = kTestStepPassed; /* to store the return value of function */
long nodeId = 112;                 /* Node-Id of DUT */
dword index = 0x9999;
dword subIndex = 0x0;
char msg[100]; /* message */
retValFunc = kTestStepPassed;
msg[0] = '\0';

/* Set the node-ID of DUT */
strncpy(msg,"Set node-ID", elCount(msg));
retValFunc = coTfsSetNodeId(nodeId);

/* call test function */
if (retValFunc == kTestStepPassed)
{
  strncpy(msg,"coTfsODChkSingleEntryNotExist", elCount(msg));
  retValFunc = coTfsODChkSingleEntryNotExist( index /*dword index*/, subIndex /*dword subIndex*/ );
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

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)