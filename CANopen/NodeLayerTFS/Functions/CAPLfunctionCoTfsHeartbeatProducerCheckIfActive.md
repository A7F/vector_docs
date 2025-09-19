# coTfsHeartbeatProducerCheckIfActive (Level 1)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

```plaintext
long coTfsHeartbeatProducerCheckIfActive( dword duration, dword producerTime, dword tolerance );
```

## Description

This function tests whether the heartbeat producer on the selected Device Under Test (DUT) is active. If heartbeat messages are detected by the DUT, then the regularity is tested across a predefined time.

The test fails if the heartbeat producer is not active or works outside of the set tolerance.

This test works passively, no SDO accesses are executed on the DUT.

## Parameters

- **duration**: Test duration in milliseconds, how long the regularity of the heartbeat producer should be tested.
- **producerTime**: Heartbeat producer time in milliseconds.
- **tolerance**: Permitted time deviation of the target device in milliseconds. It is recommended that you use an even value. The tolerated time-frame within which a message is still accepted is: `x - (tolerance/2) <= x <= x + (tolerance/2)`

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
long retValFunc = kTestStepPassed; /* to store the return value of function */
long nodeId = 112;                 /* Node-Id of DUT */

dword duration = 3000;
dword producerTime = 0x1F4;
dword tolerance = 50;

char msg[100]; /* message */

retValFunc = kTestStepPassed;
msg[0] = '\0';

/* Set the node-ID of DUT */
strncpy(msg,"Set node-ID", elCount(msg));
retValFunc = coTfsSetNodeId(nodeId);

/* call test function */
if (retValFunc == kTestStepPassed)
{
  /* Tip:
   * Enable the SYNC producer with : coTfsSDODownload(0x1017, 0, 2, 0x1F4);
   * Disable the SYNC producer with : coTfsSDODownload(0x1017, 0, 2, 0);
   */
  strncpy(msg,"coTfsHeartbeatProducerCheckIfActive", elCount(msg));
  retValFunc = coTfsHeartbeatProducerCheckIfActive( duration, producerTime, tolerance );
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
