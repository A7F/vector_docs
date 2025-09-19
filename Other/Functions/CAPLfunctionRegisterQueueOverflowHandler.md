[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionRegisterQueueOverflowHandler.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » RegisterQueueOverflowHandler

# RegisterQueueOverflowHandler

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long RegisterQueueOverflowHandler(char aCallbackfunction[], long upperLimit, long lowerLimit);
```

## Description

Registers a user-defined function which gets called whenever any events are lost on any hardware queue or on the MainQueue, or if a specific fill level of the MainQueue is reached.

Different callback functions can be defined for different sets of queue limits for performance reasons. This user-defined callback function must be of the form:

```plaintext
void QueueOverflowHandler(dword flags, dword load, qword timestamp)
```

## Parameters

- **aCallbackfunction**: Name of the user provided callback function
- **upperLimit**: If the MainQueue load exceeds this percentage limit, the callback is triggered once.
- **lowerLimit**: If the MainQueue goes below this limit, a callback can be triggered again if the **upperLimit** is exceeded.

## User-Defined Callback-Function Parameters

- **flags**: `dword`
  - Bit1: events lost on any side (runtime kernel or CANoe DE product)
  - Bit2: events lost in MainQueue
  - Bit3: events lost in any hardware queue
- **load**: `dword`
  - Current load, that triggered the queue fill level callback (0 for event loss)
- **timestamp**: `qword`
  - CANoe DE product timestamp when the event was triggered

## Return Values

—

## Example

```plaintext
on start
{
  RegisterQueueOverflowHandler("QueueOverflowHandler", 80, 1);
}
void QueueOverflowHandler(dword flags, dword load, qword timestamp)
{
  char reason[2][16] = {"MainQueue", "HardwareQueue"};
  gOverflowCounter++;
  if (flags)
    write( "<Controller> CANoe lost packets on %s", reason[(flags & 2) ? 0 : 1]);
  else
    write( "<Controller> Reached MainQueue load limit with load:%d%%", load );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
