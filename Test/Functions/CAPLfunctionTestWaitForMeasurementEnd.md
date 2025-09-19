[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForMeasurementEnd.md)

CAPL Functions » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForMeasurementEnd

# TestWaitForMeasurementEnd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TestWaitForMeasurementEnd (dword aTimeout);
```

## Description

Waits for the end of the measurement. As the final command within a test module, this function can be used to keep the test module and therefore the monitoring of constraints and conditions active. With measurement end this wait condition can be resolved. The test result and therefore also the report are not negatively impacted by the end of the measurement, if the test module does not contain any further wait commands after this one.

If a timeout time unequal to "0" is entered, the wait point is also resolved when the specified waiting time expires.

**Application**:

The test module monitors constraints and conditions. This monitoring process should be implemented precisely as long as the measurement runs.

## Parameters

- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **0**: Resume due to timeout
- **1**: Exit the wait status; measurement ended

## Example

```plaintext
// monitoring of condition is active until measurement end
dword checkId;
long result;
checkId = ChkStart_InconsistentDlc(VehicleMotion);
result = TestWaitForMeasurementEnd(5000);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
