# coTfsODAddEntrySubIndexRange (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note:** Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

```plaintext
long coTfsODAddEntrySubIndexRange( dword index, dword minSubIndex, dword maxSubIndex, dword accessType, dword entrySize, byte inMaskBuf[], dword maskBufSize, byte inValueBuf[], dword valueBufSize );

long coTfsODAddEntrySubIndexRange( dword index, dword minSubIndex, dword maxSubIndex, dword accessType, dword entrySize, qword mask, qword inValue );
```

## Description

The function adds several object entries to the internal list. The elements only differ in the given subindex. The default value can have a maximum size of 32 bit. The list is used by [coTfsODChk](CAPLfunctionCoTfsOdChk.md) and [coTfsODChkNotExist](CAPLfunctionCoTfsOdChkNotExist.md).

## Parameters

- **index**: Index of object.
- **minSubIndex**: Minimal subindex of object.
- **maxSubIndex**: Maximal subindex of object.
- **accessType**:
  - 1: readWrite
  - 2: readOnly
  - 3: writeOnly
  - 4: constant
- **entrySize**: Data size of the object in byte.
- **inMaskBuf[]**: Mask for data comparison, the size of the array must at least the same size of `maskBufSize`.
  - Bit=1: execute comparison
  - Bit=0: don't care
- **maskBufSize**: Size of buffer.
- **inValueBuf[]**: Data for comparison, the size of the array must at least the same size of `valueBufSize`.
- **valueBufSize**: Size of buffer.
- **mask**: Mask for data comparison.
- **inValue**: Data for comparison.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
long retValFunc = kTestStepPassed; /* to store the return value of function */
long nodeId = 112; /* Node-Id of DUT */

dword index = 0x2003;
dword minSubIndex = 0x1;
dword maxSubIndex = 0x3;
dword accessType = kAccessType_ReadWrite;
dword entrySize = 5; /* object size in bytes */
byte inMaskBuf[5] = {0xFF, 0xFF, 0xFF, 0xFF, 0xFF};
dword maskBufSize = 5;
byte inValueBuf[5] = {'H', 'a', 'l', 'l', 'o'};
dword valueBufSize = 5;
char msg[100]; /* message */
retValFunc = kTestStepPassed;
msg[0] = '\0';

/* Set the node-ID of DUT */
strncpy(msg,"Set node-ID", elCount(msg));
retValFunc = coTfsSetNodeId(nodeId);

/* call test function : clear test object list */
if (retValFunc == kTestStepPassed)
{
  strncpy(msg,"coTfsODClearAllEntries", elCount(msg));
  retValFunc = coTfsODClearAllEntries();
} /* if */

/* call test function : add entry range to test object list */
if (retValFunc == kTestStepPassed)
{
  strncpy(msg,"coTfsODAddEntrySubIndexRange", elCount(msg));
  retValFunc = coTfsODAddEntrySubIndexRange( index /*dword index*/, minSubIndex /*dword minSubIndex*/, maxSubIndex /*dword maxSubIndex*/, accessType /*dword accessType*/, entrySize /*dword entrySize*/, inMaskBuf /*byte inMaskBuf[]*/, maskBufSize /*dword maskBufSize*/, inValueBuf /*byte inValueBuf[]*/, valueBufSize /*dword valueBufSize*/ );
} /* if */

/* call test function : write objects in test object list */
if (retValFunc == kTestStepPassed)
{
  strncpy(msg,"coTfsODRunUserDownloadTest", elCount(msg));
  retValFunc = coTfsODRunUserDownloadTest();
} /* if */

/* call test function : check objects in test object list */
if (retValFunc == kTestStepPassed)
{
  strncpy(msg,"coTfsODRunUserUploadAndCompareTest", elCount(msg));
  retValFunc = coTfsODRunUserUploadAndCompareTest();
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
