[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsOdAddEntry.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsODAddEntry**

# coTfsODAddEntry (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

```plaintext
long coTfsODAddEntry( dword index, dword subIndex, dword accessType, dword entrySize, byte inMaskBuf[], dword maskBufSize, byte inValueBuf[], dword valueBufSize );
```

```plaintext
long coTfsODAddEntry( dword index, dword subIndex, dword accessType, dword entrySize, qword mask, qword inValue );
```

## Description

This function adds one object to the internal list of test objects. The test module manages an internal list for all object dictionary tests. Although certain object dictionary tests do not make use of all information provided, the usage of valid data is recommended.

Object entries with variable object length are supported too if the data length supplied equals 0. In this case value checks are not performed. The value mask is assumed to be open.

This function does not provide a stand-alone test. Instead it shall be used as a preparation for the test sequence functions [coTfsODChk](CAPLfunctionCoTfsOdChk.md) and [coTfsODChkNotExist](CAPLfunctionCoTfsOdChkNotExist.md).

It may be possible, that the valid data range cannot be described using just one value. Therefore it is possible to add additional values using [coTfsODAddOptEntryValue](CAPLfunctionCoTfsOdAddOptEntryValue.md). [coTfsODAddOptEntryValueRange](CAPLfunctionCoTfsOdAddOptEntryValueRange.md) allows the addition of complete value ranges. It is possible to combine both. Furthermore the valid range may overlap.

The compare mask flags all bits, which shall be compared.

## Parameters

- **index**: Checked object index.
- **subIndex**: Checked object subindex.
- **accessType**:
  - 1: readWrite
  - 2: readOnly
  - 3: writeOnly
  - 4: constant
- **entrySize**: Data size of object in bytes.
- **inMaskBuf[]**: Mask for data comparison, the size must be at least same as `maskBufSize`.
  - 0: don't care
  - 1: execute comparison
- **maskBufSize**: Size of buffer.
- **inValueBuf[]**: Data for comparison, the size must be at least same as size of `valueBufSize`.
- **valueBufSize**: Size of buffer.
- **mask**: Mask for data comparison.
- **inValue**: Data for comparison.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
long retValFunc = kTestStepPassed; /* to store the return value of function */
long nodeId = 112; /* Node-Id of DUT */

dword index = 0x1017;
dword subIndex = 0x0;
dword accessType = kAccessType_ReadWrite;
dword entrySize = 2; /* object size in bytes */
byte inMaskBuf[2] = {0xFF, 0xFF};
dword maskBufSize = 2;
byte inValueBuf[2] = {0x0, 0x0};
dword valueBufSize = 2;
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

/* call test function : add entry to test object list */
if (retValFunc == kTestStepPassed)
{
  strncpy(msg,"coTfsODAddEntry", elCount(msg));
  retValFunc = coTfsODAddEntry( index /*dword index*/, subIndex /*dword subIndex*/, accessType /*dword accessType*/, entrySize /*dword entrySize*/, inMaskBuf /*byte inMaskBuf[]*/, maskBufSize /*dword maskBufSize*/, inValueBuf /*byte inValueBuf[]*/, valueBufSize /*dword valueBufSize*/ );
} /* if */

/* call test function : check objects in test object list */
if (retValFunc == kTestStepPassed)
{
  strncpy(msg,"coTfsODChk", elCount(msg));
  retValFunc = coTfsODChk();
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
**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)