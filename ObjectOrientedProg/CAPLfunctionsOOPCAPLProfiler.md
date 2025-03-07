[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ObjectOrientedProg/CAPLfunctionsOOPCAPLProfiler.md)

[CAPL Functions](../CAPLfunctions.md) » [Classes](CAPLfunctionsOOPClassesObjects.md) » CAPLProfiler

# Class: CAPLProfiler

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

This class is used to measure how long the execution of some CAPL code – a function, or a part of a function – takes in realtime. You can use it to find code which takes longer than expected, maybe creating performance problems in the simulation.

Every `Start()` call of the profiler should be matched with a `Stop()` call, and it doesn’t make sense to let the profiler running while exiting a handler or calling one of the TestWait… functions.

You cannot create CAPLProfiler variables on the stack (with the **stack** keyword).

**Note**  
The methods are linked to the description of the corresponding CAPL function.

- [Constructor](../../Shared/CAPL/General/ClassesAndObjects.md)
- [Destructor](../../Shared/CAPL/General/ClassesAndObjects.md)
- **Method Syntax**
  - [Start](../Other/Methods/CAPLfunctionCAPLProfilerStart.md)
  - [Stop](../Other/Methods/CAPLfunctionCAPLProfilerStop.md)
  - [Reset](../Other/Methods/CAPLfunctionCAPLProfilerReset.md)
  - GetAverageCallTimeNS
  - [GetCallCount](../Other/Methods/CAPLfunctionCAPLProfilerGetCallCount.md)
  - [GetLastCallTimeNS](../Other/Methods/CAPLfunctionCAPLProfilerGetLastCallTimeNS.md)
  - [GetMaximumCallTimeNS](../Other/Methods/CAPLfunctionCAPLProfilerGetMaximumCallTimeNS.md)

•  Technical References are only available in English

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)