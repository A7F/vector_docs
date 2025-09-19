# Diagnostic Descriptions with Overloaded Responses

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

## Introduction

ODX allows the specification of more than one positive response primitive for a diagnostic service (also for negative responses). A diagnostic client (i.e. tester) cannot know which one of the valid primitives the ECU will respond a request with. Therefore it may have to try all primitives of the service until finding one that matches the received data.

## Use Cases

The following use cases exist:

- **Interpretation of diagnostic data:** If a primitive exists that matches the data without error, this primitive is displayed in the trace. Otherwise one of the primitives is used to interpret the data, and errors are indicated at the respective parameters.
- **Accessing the parameters in the response primitive in the tester:** Upon reception of the response data, CANoe will automatically use a primitive that matches without error. If no such primitive exists, CANoe will use one of the available primitives for interpretation. In this case, not all parameters may be available to the CAPL program.
- **Forcing CANoe to use a specific primitive for interpretation:** The program can ask CANoe to interpret the data in the response object using a specific existing primitive. Parameters matching the primitive definition will be available symbolically afterwards. The following functions are available for this:
  - [diagInterpretAs](Functions/CAPLfunctionDiagInterpretAs.md)
  - [diagInterpretRespAs](Functions/CAPLfunctionDiagInterpretRespAs.md)
- **Check if the response received conforms to the definition for one specific primitive:**
  - [diagCheckValidPrimitive](Functions/CAPLfunctionDiagCheckValidPrimitive.md)
  - [diagCheckValidRespPrimitive](Functions/CAPLfunctionDiagCheckValidRespPrimitive.md)
- **Initializing a diagnostic object using a specific primitive definition:** In CAPL you can initialize diagnostic objects by specifying a service qualifier. This will initialize the object with the first primitive defined, i.e. if the service defines several primitives, the program has to select one of them explicitly. This can be achieved by using this function:
  - [diagInitialize](Functions/CAPLfunctionDiagInitialize.md)
