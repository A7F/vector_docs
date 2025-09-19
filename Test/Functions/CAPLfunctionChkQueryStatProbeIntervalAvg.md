[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryStatProbeIntervalAvg.md)

**CAPL Functions** » **Test Service Library** » **Status Report Functions** » **ChkQuery_StatProbeIntervalAvg**

# ChkQuery_StatProbeIntervalAvg

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
double ChkQuery_StatProbeIntervalAvg (dword aCheckId)
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
check.QueryStatProbeIntervalAvg()
```

## Description

Returns the average timely distance between 2 consumed message events.

## Parameters

- **aCheckId**: Identifier of the queried Check.

## Return Values

- **< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)

  **Note**: There is a meaningful value available and a positive return value is supplied even if the check has not generated any event.

- **> 0**: Average timely distance

## Example

```plaintext
double result;
dword checkId;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = ChkQuery_StatProbeIntervalAvg(checkId);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
