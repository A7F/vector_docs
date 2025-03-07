[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForTextEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForTextEvent

# TestWaitForTextEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TestWaitForTextEvent(char aText[], dword aTimeout);
```

## Description

Waits for the signaling of the specified textual event from the individual test module. A signaling from another test module does not affect this wait instruction.

Should this event not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

## Parameters

- **aText**: Any (meaningful) textual event name
- **aTimeout**: Maximum time that should be waited [ms]  
  (Transmission of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```plaintext
// waits for the occurrence of text event "ErrorFrame occurred!"
long result;
result = TestWaitForTextEvent("ErrorFrame occurred!", 3000);

// handler 'on errorFrame' signals event
on errorFrame
{
   TestSupplyTextEvent("ErrorFrame occurred!");
}
```

[TestJoinTextEvent](CAPLfunctionTestJoinTextEvent.md) • [TestSupplyTextEvent](CAPLfunctionTestSupplyTextEvent.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)