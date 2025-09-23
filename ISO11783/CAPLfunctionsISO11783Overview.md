[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/CAPLfunctionsISO11783Overview.md)

[CAPL Functions](../CAPLfunctions.md) » ISO11783 CAPL Functions

# ISO11783 CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

Only available with Option ISO11783.

---

## ISO11783 Interaction Layer

- [CAPL Functions](ISOInteractionLayer/CAPLfunctionsISOILOverview.md)
- [Error Codes](../CAPLfunctionsISOj1939ErrorCodes.md)

The ISO11783 Interaction Layer (short ISO11783 IL) is a library for quick and easy modeling of ECUs on the ISOBUS. In addition to functions for signal-based access to the ISOBUS (similar to those of the J1939 Interaction Layer), the ISO11783 IL offers many ways to simulate the entire communication between a simulated ISO11783 node and a virtual terminal, task controller or data logger in a very simple way. In addition, the ISO11783 IL simplifies simulation of an auxiliary input node considerably.

The ISO11783 Interaction Layer offers the following functionality:

- Signal-based access to the ISOBUS
- Sending messages in response to a request
- Support of Address Claiming
- Support of transport protocols
- Communication with a Virtual Terminal and one or more auxiliary ECUs (Object Pool API)
- Communication with a Task Controller (Process Data API)
- Simulation of a File Server via the CAPL interface (File Server API)

## ISO11783 File Server Interaction Layer (FS IL)

- [CAPL Functions](ISOInteractionLayerFS/CAPLfunctionsISOILFSOverview.md)
- [Error Codes](../CAPLfunctionsISOj1939ErrorCodes.md)

With the help of the FS IL you can expand a simulation node in an ISOBUS network into a File Server without a visible user interface. FS IL offers the following functionality:

- Varied configuration of the File Server: File Server version, support of long filenames, etc.
- Configuration of the File Server using CAPL commands: For example, Importing files and directories to establish an initial environment.
- Manipulation of response and status messages of the File Server (fault injection).

## ISO11783 Node Layer

- [CAPL Functions](ISONodeLayer/CAPLfunctionsISONLOverview.md)
- [Error Codes](ISONodeLayer/CAPLfunctionsISONLErrorCodes.md)

The ISO11783 node layer simplifies the simulation of an ISO11783 node with CAPL. The ISO11783 node layer offers the following functionality:

- Address claiming
- Node table
- Sending and reception of parameter groups
- Transport protocols
- Is used by generated CAPL programs
- Communication with a Virtual Terminal and one or more auxiliary ECUs (Object Pool API)
- Communication with a Task Controller (Process Data API)

## ISO11783 Virtual Terminal Interaction Layer (VT IL)

- [CAPL Functions](ISOInteractionLayerVT/CAPLfunctionsISOILVTOverview.md)
- [Error Codes](../CAPLfunctionsISOj1939ErrorCodes.md)

With the help of the VT IL you can expand a simulation node in an ISOBUS network into a Virtual Terminal without a visible user interface. VT IL offers the following functionality:

- Varied configuration of the Virtual Terminal: VT version, size of masks, number of buttons, etc.
- Handling of the Virtual Terminal using CAPL commands: For example, Pressing of a soft key or entering a value.
- Definition of current object values from a transferred object pool. (can also be used in passive mode in parallel with a real Virtual Terminal.)
- Connection of object values from an object pool to system variables.
- Manipulation of response messages of the Virtual Terminal (fault injection).
- Manipulation of the VT Status message (fault injection).

## ISO11783 Task Controller Interaction Layer (TC IL)

- [CAPL Functions](ISOInteractionLayerTC/CAPLfunctionsISOILTCOverview.md)
- [Error Codes](../CAPLfunctionsISOj1939ErrorCodes.md)

With the help of the TC IL you can expand a simulation node in an ISOBUS network into a Task Controller without a visible user interface. TC IL offers the following functionality:

- Varied configuration of the Task Controller: TC version, size of masks, number of buttons, etc.
- Handling of the Task Controller using CAPL commands: For example, Starting/stopping a task, sending/requesting the value of a process variable
- Defining current process variable values and device properties. (can also be used in passive mode in parallel with a real Task Controller)
- Connecting process variables to system variables.
- Manipulation of response messages of the Task Controller (fault injection).
- Manipulation of the TC Status message (fault injection).

---
