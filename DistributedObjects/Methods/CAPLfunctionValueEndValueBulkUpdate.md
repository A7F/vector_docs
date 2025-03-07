[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctionValueEndValueBulkUpdate.md)

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » valueHandle::EndValueBulkUpdate

# valueHandle::EndValueBulkUpdate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
void valueHandle::EndValueBulkUpdate();
```

## Description

Ends a bulk update started with [valueHandle::BeginValueBulkUpdate](CAPLfunctionValueBeginValueBulkUpdate.md) causing the triggering of change/update events for value updates since [valueHandle::BeginValueBulkUpdate](CAPLfunctionValueBeginValueBulkUpdate.md).

## Parameters

—

## Return Values

—

## Example

```plaintext
SomeDO.SomeComplexMember.BeginValueBulkUpdate();
$SomeDO.SomeComplexMember.MemA = 42;
$SomeDO.SomeComplexMember.MemB = 0;
SomeDO.SomeComplexMember.EndValueBulkUpdate();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)