[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/CAPLfunctionsCANoeILOverviewExecContext.md)

[CAPL Functions](../CAPLfunctions.md) » [CANoe IL](CAPLfunctionsCANoeILOverview.md) » Functions in the Execution Context

# Functions in the Execution Context

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Node Context in the Simulation Setup
The interaction layer is generally executed in the node context. This means that the CAPL interface can be used only within this node. In this way it is ensured that the relationship between a node and its model is maintained.

### Global Functions in the Simulation Setup
Various control and disturbance functions are provided for implementing a central control node in the Simulation Setup.

### Functions in the Test Module
Various control and disturbance functions are provided for implementing tests in the CAPL test module.

- [ILActivateClamp15](Functions/CAPLfunctionILActivateClamp15.md)
- [ILDeactivateClamp15](Functions/CAPLfunctionILActivateClamp15.md)
- [ILControlInit](Functions/CAPLfunctionILControlInit.md)
- [ILControlStart](Functions/CAPLfunctionILControlStart.md)
- [ILControlStop](Functions/CAPLfunctionILControlStop.md)
- [ILControlWait](Functions/CAPLfunctionILNodeControlWait.md)
- [ILControlResume](Functions/CAPLfunctionILNodeControlResume.md)
- [ILControlSimulationOff](Functions/CAPLfunctionILNodeControlSimulationOff.md)
- [ILControlSimulationOn](Functions/CAPLfunctionILNodeControlSimulationOn.md)
- [ILErrno](Functions/CAPLfunctionILErrno.md)
- [ILSetResultString](Functions/CAPLfunctionILSetResultString.md)
- [ILFaultInjectionDisableMsg](Functions/CAPLfunctionILFaultInjectionDisableMsg.md)
  - [ILDisableMSG](Functions/CAPLfunctionILDisableMsg.md)
  - [TestDisableMsg](../Test/Functions/CAPLfunctionTestDisableMsg.md)
- [ILFaultInjectionEnableMsg](Functions/CAPLfunctionILFaultInjectionEnableMsg.md)
  - [ILEnableMSG](Functions/CAPLfunctionILEnableMsg.md)
  - [TestEnableMsg](../Test/Functions/CAPLfunctionTestEnableMsg.md)
- [ILFaultInjectionResetAllFaultInjections](Functions/CAPLfunctionILFaultInjectionResetAllFaultInjections.md)
  - [TestResetAllFaultInjections](../Test/Functions/CAPLfunctionTestResetAllFaultInjections.md)
- [ILFaultInjectionResetMsgCycleTime](Functions/CAPLfunctionILFaultInjectionResetMsgCycleTime.md)
  - [TestResetMsgCycleTime](../Test/Functions/CAPLfunctionTestResetMsgCycleTime.md)
- [ILFaultInjectionResetMsgDlc](Functions/CAPLfunctionILFaultInjectionResetMsgDlc.md)
  - [TestResetMsgDlc](../Test/Functions/CAPLfunctionTestResetMsgDlc.md)
- [ILFaultInjectionSetMsgDlc](Functions/CAPLfunctionILFaultInjectionSetMsgDlc.md)
  - [TestSetMsgDlc](../Test/Functions/CAPLfunctionTestSetSetMsgDlc.md)
- [ILFaultInjectionSetMsgCycleTime](Functions/CAPLfunctionILFaultInjectionSetMsgCycleTime.md)
  - [TestSetMsgCycleTime](../Test/Functions/CAPLfunctionTestSetMsgCycleTime.md)
- [ILSetMsgEvent](Functions/CAPLfunctionILSetMsgEvent.md)
  - [TestSetMsgEvent](../Test/Functions/CAPLfunctionTestSetMsgEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)