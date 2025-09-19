[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/CAPLfunctionsTSLSampleCode.md)

## Stimulus Generator: Sample Code StmCreate_Ramp

[CAPL Functions](../CAPLfunctions.md) » [Test Service Library](CAPLfunctionsTSLStimulusOverview.md) » Stimulus Generator: Sample Code StmCreate_Ramp

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Sample Code

```plaintext
variables
{
// Local message buffer
message StmMsg lStmMsg;
// Defines the cycle for output of the stimulated signals
dword gOutTime;
msTimer tOutStmMsg;
// Remember the handles for the different stimuli:
dword mRampId = 0;
// Description of the stimuli functions in the demo.
// - Creation of stimuli in the pre-start event
// - Control of the stimulated signals by environment variable
}
```

```plaintext
on preStart
{
// Initialize the TSL functionality.
// TSL should be initialized with "user" or "developer".
// The "user" setting is very silent and reports only severe problems.
// The "developer" setting is more verbose and reports useful information
ChkConfig_Init("user");
// Set precision of timers to us (10^-6 seconds)
ChkConfig_SetPrecision(6);
// Create the ramp stimulus
mRampId = StmCreate_Ramp(lStmMsg, StmMsg::RampSig,-10,10,5,300,200,100,400);
}
```

```plaintext
on start
{
gOutTime = getValue(EnvOutTime);
SetTimer(tOutStmMsg, gOutTime);
}
```

```plaintext
on timer tOutStmMsg
{
// Output of the message
output(lStmMsg);
SetTimer(tOutStmMsg, gOutTime);
}
```

```plaintext
// Start and stop the ramp stimuli
on envVar EnvCtrlRamp
{
long lRet;
if(getValue(this))
{
 lRet = StmControl_Start(mRampId);
}
else
{
 lRet = StmControl_Stop(mRampId);
}
}
```

```plaintext
// Reset the ramp stimuli
on envVar EnvResetRamp
{
long lRet;
if(getValue(this))
{
 if(mRampId)
  lRet = StmControl_Reset(mRampId);
}
}
```

```plaintext
// New settings for the ramp stimuli
on envVar EnvRampApply
{
long lRet;
if(getValue(this))
{
 if(mRampId)
 { 
  lRet = StmControl_Destroy(mRampId);
  mRampId = 0;
 }
 mRampId = StmCreate_Ramp( lStmMsg, 
                           StmMsg::RampSig,
                           getValue(EnvRampValueA),
                           getValue(EnvRampValueB),
                           getValue(EnvRampCycleTime),
                           getValue(EnvRampTimeUp),
                           getValue(EnvRampTimeHigh),
                           getValue(EnvRampTimeDown),
                           getValue(EnvRampTimeLow));
 if(getValue(EnvCtrlRamp))
 {
  lRet = StmControl_Start(mRampId);
 }
}
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
