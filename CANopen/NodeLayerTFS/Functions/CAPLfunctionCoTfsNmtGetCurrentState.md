[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsNmtGetCurrentState.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsNmtGetCurrentState**

# coTfsNmtGetCurrentState (Level 1)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

```plaintext
long coTfsNmtGetCurrentState( dword nmtState[1] );
```

## Description

This function returns the current device status of the DUT (Device Under Test). The current state is checked with heartbeat and guarding mechanisms.

For this, there is first an attempt to configure a heartbeat producer in the DUT (object 0x1017). The heartbeat message contains the current device status. If the DUT should not make a heartbeat producer available, a remote guarding frame is sent to the DUT. The DUT responds with the corresponding guarding response. The procedure is repeated again. The second response is evaluated and contains the device status. The CANopen® specification provides that a CANopen® device supports at least one of the two modes.

**Note**  
If the heartbeat producer is already active, it will be restored at the end.

## Parameters

- **nmtState**: Current device status (data field)
  - 0: boot-up
  - 4: stopped
  - 5: operational
  - 127: pre-operational

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
long retValFunc = kTestStepPassed; /* to store the return value of function */
long nodeId = 112; /* Node-Id of DUT */

dword nmtState[1] = 0;
char msg[100]; /* message */
retValFunc = kTestStepPassed;
msg[0] = '\0';

/* Set the node-ID of DUT */
strncpy(msg,"Set node-ID", elCount(msg));
retValFunc = coTfsSetNodeId(nodeId);

/* call test function */
if (retValFunc == kTestStepPassed)
{
  strncpy(msg,"coTfsNMTGetCurrentState", elCount(msg));
  retValFunc = coTfsNmtGetCurrentState( nmtState );

  /* evaluation of returned value */
  switch(nmtState[0])
  {
    case kNMTState_BootUp : /* Initialization/Boot-up */
    {
      write( "DUT is in NMT state Initialization/Boot-up");
      break;
    } /* case */
    case kNMTState_Stopped : /* Stopped */
    {
      write( "DUT is in NMT state Stopped");
      break;
    } /* case */
    case kNMTState_Operationa1 : /* Operational */
    {
      write( "DUT is in NMT state Operational");
      break;
    } /* case */
    case kNMTState_PreOperational : /* Pre-operational */
    {
      write( "DUT is in NMT state Pre-operational");
      break;
    } /* case */
  } /* switch */
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