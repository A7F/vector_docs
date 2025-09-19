[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md)

**CAPL Functions** » **Diagnostics** » Connection of the Communication Layer

# Diagnostics: Connection of the Communication Layer

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

The diagnostic commands in CAPL allow access to the diagnostic services and data using symbols that were defined in the CANdela description file. For communication, this data must be transmitted, where two ways are available:

- In a tester node or test module, a call to [diagSetTarget](Functions/CAPLfunctionDiagSetTarget.md) suffices. It will connect the tester to the ECU via the so-called built-in diagnostic channel provided by CANoe.
- In an ECU simulation, it is necessary to implement the **CAPL callback interface**. This interface consists of a set of functions implemented in CAPL that are called by CANoe to trigger actions, and special CAPL functions implemented by CANoe that forward transport protocol events to CANoe.

This interface may also be used in tester nodes and test modules if direct access to the transport protocol is necessary, e.g., to perform fault injection.

## CAPL Callback Interface for Diagnostics

- [_Diag_SetChannelParameters](Functions/CAPLfunctionDiagSetChannelParameters.md): This function is called by CANoe to indicate that a new communication "channel" to the ECU or tester should be opened. Typically the settings configured for the ECU are queried and the transport protocol layer is configured.
- [_Diag_DataRequest](Functions/CAPLfunctionDiagDataRequest.md): CANoe triggers the sending of data to the peer, i.e., in an ECU simulation, the bytes representing the response primitive will be given to be forwarded to the transport protocol. In a tester, the bytes represent the request primitive.
- [_Diag_SendFunctional](Functions/CAPLfunctionDiagSendFunctionalCallback.md) (in testers only): CANoe triggers the functional sending of a request.
- [_Diag_SetupChannelReq](Functions/CAPLfunctionDiagSetupChannelRequest.md) (in testers only): For connection-oriented transport protocols, the tester has to establish a communication channel to the ECU. Once the channel is available, the tester has to call [diag_SetupChannelCon](Functions/CAPLfunctionDiagSetupChannelCon.md).

For connectionless transport protocols, `Diag_SetupChannelCon` can be called immediately.

Depending on the transport protocol implementation used, the events the CAPL program receives have to be forwarded to CANoe.  
Please refer to these functions for details:

- [diag_DataInd](Functions/CAPLfunctionDiagDataInd.md)
- [diag_ErrorInd](Functions/CAPLfunctionDiagErrorInd.md)
- [diag_DataCon](Functions/CAPLfunctionDiagDataCon.md)
- [diag_FirstFrameInd](Functions/CAPLfunctionDiagFirstFrameInd.md)
- [diag_ClosedChannelInd](Functions/CAPLfunctionDiagClosedChannelInd.md)
- [diag_SetDataSegmentation](Functions/CAPLfunctionDiagSetDataSegmentation.md)
- [diag_SetupChannelCon](Functions/CAPLfunctionDiagSetupChannelCon.md)

A reference implementation of the [CAPL Callback Interface in CANoe](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf')) is available for the networks CAN, LIN, FlexRay (FlexRay TP AUTOSAR and FlexRay TP ISO) and DoIP/HSFZ using typical transport protocols for those bus systems.

For special applications in the course of ECU test and development, those functions may be modified, e.g., for inducing transmission errors for robustness tests.

The reference implementations are available as include files (*.cin) in the CANoe installation folder **Reusable\CAPL_Includes\Diagnostics** you find in the same directory like the CANoe sample configurations.

In order to use them, you simply need to do the following steps:

1. Include the respective CIN file into your CAPL simulation nodes, test nodes, test modules, and test case libraries.
2. Define the following global variables in your CAPL code:
   - **char gECU[]**  
     gECU is the name of the respective node, e.g., of a simulated ECU, necessary for identifying the node in case of error messages in the [Write Window](../../CANoeCANalyzer/Windows/Write/WriteWindow.md). In case of FlexRay, it needs to contain the name of the database node.
   - **int cIsTester**  
     cIsTester is a flag indicating whether the node serves as a tester (cIsTester=1) or an ECU (cIsTester=0).

3. Add the respective transport protocol DLL to your CAPL node as a component, either by assigning it in the network description database or by adding it in the **Components** tab of the **Node Configuration** dialog.
4. Implement the diagnostics behavior of your CAPL node using CAPL diagnostics functions, [on diagRequest](EventProcedures/CAPLfunctionOnDiagRequest.md) and [on diagResponse](EventProcedures/CAPLfunctionOnDiagResponse.md) handlers.
5. Make sure there is a link between the diagnostic description and your CAPL code using the CAPL functions [diagSetTarget](Functions/CAPLfunctionDiagSetTarget.md) (in a **tester node**) or [diagInitEcuSimulation](../KLine/Functions/CAPLfunctionDiagInitEcuSimulation.md) (in an **ECU simulation**). Alternatively, you may choose **Assign to database node** as usage of the diagnostic description in the **Configuration|Diagnostics/ISO TP...** dialog (where available).

The following example shows a very simple CAPL ECU simulation node.

You may add additional [on diagRequest `<service>`](EventProcedures/CAPLfunctionOnDiagRequest.md) handlers for all diagnostic services you want to support with your simulation and change the value of **gECU** to the ECU qualifier you defined in the **Diagnostics/ISO TP…** dialog. Additionally, you might need to adapt the service name for the **Tester Present** service (in this example: **TesterPresent_Process**) to the service identifier specified in your diagnostic description:

```plaintext
includes
{
  // Include the CAPL Callback Interface (CCI) reference implementation for CAN TP
  #include "Diagnostics\CCI_CanTP.cin"
}

variables
{
  // Define constants necessary for the CCI reference implementation
  char gECU[20]="CAN_ECU"; // ECU qualifier defined in the
  // "Configuration|Diagnostics/ISO TP..." dialog
  int cIsTester=0;         // This is a simulation node, no tester node
}

on preStart
{
  // Provide the link to the configured diagnostic description
  diagInitEcuSimulation(gECU);
}

// Very simple implementation of diagnostics services supported by this simulation
// Only "Tester Present" is answered by a positive response, all other services by negative response
on diagRequest *
{
  diagResponse this resp;
  diagSendNegativeResponse(resp, 0x11); // Service not supported
}

on diagRequest TesterPresent_Process
{
  diagResponse this resp;
  diagSendPositiveResponse(resp);
}
```

[Expanded Functions in CAPL](CAPLfunctionsDiagnosticsExpandedFunctions.md) • [Basic CAPL Procedure for an ECU Implementation](CAPLfunctionsDiagnosticsECUImplementation.md) • [Basic CAPL Procedure for a Tester Implementation](CAPLfunctionsDiagnosticsTestImplementation.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)