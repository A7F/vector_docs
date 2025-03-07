[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/CAPLfunctionsTSLCheckControlCommands.md)

[CAPL Functions](../CAPLfunctions.md) » [Test Service Library](CAPLfunctionsTSLOverview.md) » Status Report Functions

# Test Service Library: Commands to Control Checks

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Usage in Test Modules as Constraints/Conditions

In CAPL test modules it's recommended to use Checks as Constraints or Conditions and to create and start them straight before their usage (ChkStart_...).

```plaintext
testcase TC ()
{
...
chkid = ChkStart_MsgRelCycleTimeViolation (StatusMsg, 0.8, 1.2);
TestAddConstraint (chkid);
...
TestRemoveConstraint (chkid);
}
```

In this case there's no need to use Callback functions. In addition it's usually not necessary to query test results since violations of the test specification directly influence the test result and will be documented in the test report together with some relevant information.

In CAPL Simulation Nodes Checks can be used and controlled directly. In principle this works in CAPL test modules, too. Nevertheless it is not recommended and - apart from some rare special cases - there are no advantages in doing so.

## Using checks in CAPL Simulation Nodes

- Define a new check and start immediately after you finished the definition
- Define a new check for later use (recommended!)
- Start a predefined check (recommended!)

## Recommendation

You can define all checks "on_preStart" and use the control functions during a measurement to start/stop a check.

## Check Lifecycle Control

Checks may be stopped, (re-)started, reset and destroyed:

- Once stopped, the check will no longer test the occurrence of the event condition. Its state is guaranteed to stay the same until it is restarted.
- A check that has been stopped or created earlier and has not been activated yet, can be activated again and will generate events if error conditions occur.
- The state of the check may be reset, initializing it.
- When destroyed, the reference to the check loses validity and no information on its previous state can be queried. Any later access to the check will lead to a fatal error.

## Note

For test programs of typical size and duration, there is no necessity to destroy the checks in CAPL. Only those rare cases with extremely long running tests and dynamic check creation need to destroy checks to prevent a lack of memory.

- Checks are automatically deleted on stop of measurement.

## Check Control CAPL Functions

For the check control there are the following functions to influence. These functions can be used to turn off checking in not relevant time (e.g. with changes of the network hardware), and to continue checking. These control functions can also be used to setup dependencies between checks:

- [ChkControl_Start](Functions/CAPLfunctionChkControlStart.md): Begins or continues checking the event condition.
- [ChkControl_Stop](Functions/CAPLfunctionChkControlStop.md): Turns off the checking of the event condition.
- [ChkControl_Reset](Functions/CAPLfunctionChkControlReset.md): Initializes the status of the check.
- [ChkControl_Destroy](Functions/CAPLfunctionChkControlDestroy.md): Destroys the check.

© Vector Informatik GmbH

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)