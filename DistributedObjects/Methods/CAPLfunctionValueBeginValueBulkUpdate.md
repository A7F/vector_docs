# valueHandle::BeginValueBulkUpdate

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
void valueHandle::BeginValueBulkUpdate();
```

## Description

Begins a bulk update. This improves the performance of complex value updates. Update/change handlers are only triggered after a call to [valueHandle::EndValueBulkUpdate](CAPLfunctionValueEndValueBulkUpdate.md).

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
