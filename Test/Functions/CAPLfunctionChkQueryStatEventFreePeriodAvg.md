[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryStatEventFreePeriodAvg.md)

**CAPL Functions** » **Test Service Library** » **Status Report Functions** » **ChkQuery_StatEventFreePeriodAvg**

# ChkQuery_StatEventFreePeriodAvg

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
double ChkQuery_StatEventFreePeriodAvg (dword aCheckId);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
check.QueryStatEventFreePeriodAvg();
```

## Description

Returns the average timely distance between events and check starts/stops.

**Note**: Among other things with this function the average cycle time of a cyclic message can be queried.

## Parameters

- **aCheckId**: Identifier of the queried Check.

## Return Values

- **< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)

  **Note**: There is a meaningful value available and a positive return value is supplied even if the check has not generated any event.

- **≥ 0**: Average timely distance in the current precision

## Example

```plaintext
double result;
dword checkId;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = ChkQuery_StatEventFreePeriodAvg(checkId);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)