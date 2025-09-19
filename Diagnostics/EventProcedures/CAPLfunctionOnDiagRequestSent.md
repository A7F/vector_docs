# on diagRequestSent

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**

The following syntax forms require a defined target ECU by calling [diagSetTarget(char ecuQualifier[])](../Functions/CAPLfunctionDiagSetTarget.htm) beforehand. When using these forms, no semantic check can be performed at compile-time, so no warnings will be emitted for nonexistent diagRequests.

- form 1
- form 2
- form 3
- form 4

## Function Syntax

`on diagRequestSent`

## Description

The procedure is sub-divided into the following events; the first matching event procedure (top-down) is called:

- `on diagRequestSent <service>` // form 1
  - Is called when a request is sent completely in the Tester simulation that belongs to the indicated diagnostic service.

- `*on diagRequestSent <class>::*` // form 2
  - Is called when the service of the sent request belongs to the specified class.

- `on diagRequestSent *` // form 3
  - Is called when no other event procedure matches.
  - This procedure may therefore be called for several services!

- `on diagRequestSent ECU.<service>` // form 4
  - Is called when a request is sent completely in the Tester simulation that belongs to the indicated diagnostic service.

- `*on diagRequestSent ECU.<class>::*` // form 5
  - Is called when the service of the sent request belongs to the specified class.

- `on diagRequestSent ECU.*` // form 6
  - Is called when no other event procedure matches.
  - This procedure may therefore be called for several services!

**Note**

Please note that, after every sending of a request, all responses are signaled only to the sender. Diagnostic requests that are sent from the Diagnostic Console are thus invisible for a CAPL program as are the received responses. Similarly, no responses to requests sent from a CAPL program are displayed in the Diagnostic Console.

## Example

**Example 1**

```plaintext
on diagRequestSent *
{
   // A request was sent, therefore on LIN the schedule has to be changed
   linChangeSchedTable( cSchedulingTableForDiagResponse);
}

on diagRequestSent ECU_SoftReset
{
   // The ECU will perform a reset for some time, so inform the rest of the CAPL program
   gECUisResetting = 1;
}
```

**Example 2**

For event handlers, it is also possible to specify an ECU qualifier to filter specific events. And all services that belong to the same diagnostic class can be processed in one handler.

```plaintext
// process all diagnostic requests from ECU1 without better match here
On diagResponse ECU1.*
{
   // access the response using 'this'
}

// Only Service1 responses from ECU1 will be reported here
On diagResponse ECU1.Service1
{
}

On diagRequestSent ECU2.*
{
   // ECU2 is using a transport protocol with confirmations
   Write( "ECU2 has confirmed reception of event");
}

On diagResponse ECU1.Class1::*
{
   write( "A response for a service of Class1 was received");
}
```
