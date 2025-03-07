[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsNmtRequest.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsNmtRequest**

# coTfsNmtRequest (Level 1)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

```plaintext
long coTfsNmtRequest( dword command );
long coTfsNmtRequest( dword command, dword broadcastFlag );
```

## Description

This function sends a NMT request.

For selection of the command parameter value 129 or 130 the function waits for the following boot-up message; otherwise the function attempts to check the device status of the DUT via the guarding or heartbeat mechanism.

For this, there is first an attempt to configure a heartbeat producer in the DUT (object 0x1017). The heartbeat message contains the current device status. If the DUT should not make a heartbeat producer available, a remote guarding frame is sent to the DUT. The DUT responds with the corresponding guarding response. The procedure is repeated again. The second response is evaluated and contains the device status. The CANopen® specification provides that a CANopen® device supports at least one of the two modes.

If the stop command (`command=2`) is sent, it is not checked if the DUT switches to stopped state.

**Note**  
If the heartbeat producer is already active, it will be restored at the end.

## Parameters

- **command**
  - 1: start
  - 2: stop
  - 128: enter pre-operational
  - 129: reset node
  - 130: reset communication

- **broadcastFlag**
  - !=0: NMT message is sent to all nodes (broadcast)

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
long retValFunc = kTestStepPassed; /* to store the return value of function */
long nodeId = 112; /* Node-Id of DUT */

dword command = kCommandSpecifier_ResetCommunication;

char msg[100]; /* message */
retValFunc = kTestStepPassed;
msg[0] = '\0';

/* Set the node-ID of DUT */
strncpy(msg,"Set node-ID", elCount(msg));
retValFunc = coTfsSetNodeId(nodeId);

/* call test function */
if (retValFunc == kTestStepPassed)
{
  strncpy(msg,"coTfsNMTRequest", elCount(msg));
  retValFunc = coTfsNmtRequest( command );
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