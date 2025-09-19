[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetWaitEventSysVarData.md)

**CAPL Functions** » **Test Feature Set** » **TestGetWaitEventSysVarData**

# TestGetWaitEventSysVarData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long testGetWaitEventSysVarData(dword index, float & value); // form 1`
- `long testGetWaitEventSysVarData(dword index, char value[], dword length); // form 2`
- `long testGetWaitEventSysVarData(dword index, float value[], dword length); // form 3`
- `long testGetWaitEventSysVarData(dword index, int64 & value); // form 4`

## Description

Retrieves the system variable value that has led to the resume of a joined wait statement.

## Parameters

- **value**: The variable will be filled with the current value of the system variable value.
- **length**: Length of the char or float array. Used for system variables of type string, integer array or float array.
- **index**: Number of the "joined event" corresponds with the return value of "testJoin...".

## Return Values

- **0**: Data access successful
- **-1**: Data access could not be executed, the last event was not a system variable event
- **-2**: Data access not possible, wrong function was used

## Example

```plaintext
// add sysVar event to the current set of "joined events" and get the sysVar value
dword index = 0;
float sysValue = 0;
TestJoinSysVarEvent(MySysVar);
// ... other join events
index = TestWaitForAnyJoinedEvent(2000);

TestGetWaitEventSysVarData(index, sysValue);
```

[TestWaitForSysVar](CAPLfunctionTestWaitForSysVar.md) • [TestJoinSysVarEvent](CAPLfunctionTestJoinSysVarEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
