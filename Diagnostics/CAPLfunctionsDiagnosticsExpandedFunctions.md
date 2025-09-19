[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/CAPLfunctionsDiagnosticsExpandedFunctions.md)

**CAPL Functions** » [Diagnostics](CAPLfunctionsDiagnosticsOverview.md) » Expanded Functions in CAPL

# Diagnostics: Expanded Functions in CAPL

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

As of CANoe 5.0, it is possible to access CANdela Studio diagnostic descriptions within [CAPL programs](CAPLfunctionsDiagnosticsOverview.md):

- With the configuration of the diagnostic observer, a description can be assigned to a simulation node. The CAPL program of this node is then regarded as an implementation of the diagnostic functionality of this ECU ([ECU implementation](CAPLfunctionsDiagnosticsECUImplementation.md)) and thus all defined services are recognized.
- For the implementation of a [diagnostic tester](CAPLfunctionsDiagnosticsTestImplementation.md), it is possible to select the target ECU in the CAPL program, i.e., to choose the corresponding diagnostic description. This can be done either by using the CAPL function [DiagSetTarget](Functions/CAPLfunctionDiagSetTarget.md) or by specifying the ECU qualifier in the definition of the diagRequest or diagResponse object.
- Request and response objects can be generated using their qualifier in combination with the respective ECU qualifier.
- In the CAPL program, diagnostic services, parameters, and parameter values can be accessed symbolically.
- The arrival of requests and responses can be processed via event procedures.
- The [connection to the communication layer](CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md) occurs either via the **built-in diagnostic channel** or via CAPL callbacks – the so-called **CAPL Callback Interface (CCI)** –, whereby the full control over the communication is retained for development and test. For standard applications, corresponding CCI reference implementations are already available.
- [Usage in Test modules](CAPLfunctionsDiagnosticsUsingFunctionTestCase.md): Effective with CANoe 5.0 SP3, it is possible within test modules to wait on diagnostic events. After sending a request, you can wait for a response without programming a state machine. You have access to the response of the ECU.

Starting with CANoe DE product 7.5, it is also possible to use [basic diagnostic descriptions](../../CANoeCANalyzer/Diagnostics/BasicDiagnostics/BasicDiagnostics.md) from within CAPL for the tester side. Details whether a function is supported for basic diagnostics can be found in the documentation of each function.

## Limitations

Please note the following limitations of the diagnostic functions:

- Presently, a node can only implement the diagnostic functions of one ECU.

## Additional Remarks

- To specify a service or simple parameter, its qualifier from the diagnostic description is used. You can drag and drop the service qualifier from the Symbol Explorer.

The qualifier of a complex parameter can be found in CANdelaStudio with the Properties of the parameter.

**Note:** Do not confuse the identifier with the language-dependent name of the object since then the object cannot be identified!

- In order to assign an object with a variable number of parameters, proceed as follows: if the parameter list is defined in CANdelaStudio as iterative parameters with a number, then first this parameter (e.g., "NUMBER_OF_DTC") must be set. Then call `DiagResize(response)`, which makes space for the actual parameters. These can be set with the `DiagSetComplexParameter` functions.

**Note:** The length of the elements of a qualifier path from the CANdela description file is limited to 50 characters in the CAPL Compiler. Longer names may exceed this limit, but the CAPL program cannot be compiled. Nevertheless, it is possible to specify the qualifier path as a text string in quotation marks: "`<Qualifier Path>`". In this case, the qualifier path may be up to 255 characters in length.

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)