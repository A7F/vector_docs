[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/CAPLfunctionsDiagnosticsErrorCode.md)

# Return Values

[CAPL Functions](../CAPLfunctions.md) » [Diagnostics](CAPLfunctionsDiagnosticsOverview.md) » Error Codes

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

The following values can be returned:

- **0**: No error, success.
- **>0**: Number, e.g. length of the given text.
- **-100**: The input provided on function call is not consistent or sufficient. Check the arguments provided to the function call.
- **-99**: The object's response is pending, therefore cannot delete it. Delay the operation until the object is no longer accessed.
- **-98**: The handle is not assigned to a diagnostic object. Check that the initialization of the object worked, i.e. `diagSetTarget` was successful.
- **-97**: The parameter does not exist in this object, or is constant. Make sure that the parameter exists in the diagnostic object.
- **-96**: Function not implemented yet.
- **-95**: Accessing CANdelaLib lead to error '...' for '...' Parameter or object '...' not defined! Make sure the parameter is defined in the accessed diagnostic object.
- **-94**: Diagnostics was not initialized for the node, i.e. no SetEcu/Target called. Make sure `diagSetTarget` is called and sets an existing target successfully.
- **-93**: The specified callback was not found. Please refer to [Diagnostics: Connection of the Communication Layer](CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md) for details.
- **-92**: There was an error on TP level. Check the Write window for further information.
- **-91**: Only one request/response can be sent at a time! Make sure that the processing of the previous object is finished.
- **-90**: Test function outside TestCase, or Tester-only function called in ECU, or vice-versa. Requests can only be sent from nodes configured as tester.
- **-89**: No Seed & Key library was specified. Configure a Seed & Key DLL.
- **-88**: The Seed & Key library did not contain a matching Seed & Key function. Configure a Seed & Key DLL that holds the expected Seed & Key function.
- **-87**: The Seed & Key library couldn't be loaded. Ensure that the correct Seed & Key path and filename is configured.
- **-86**: The buffer was too small. Increase the buffer size.
- **-85**: The seed array size is too large. Decrease the seed array size.
- **-84**: The security level is invalid. Use a correct security level.
- **-83**: The variant is invalid. Use a supported variant.
- **-82**: An unspecified error occurred.
- **-81**: The function cannot perform the action because of wrong HW. Ensure correct HW devices.
- **-80**: No matching request was found to perform the action.
- **-79**: No diagnostic channel found.
- **-78**: No suitable class or request was found. Ensure that the qualifiers are defined in the diagnostic description.
- **-77**: A timeout happened. The ECU did not send a response for the request.
- **-76**: Transmission failed. The request or response could not be sent.
- **-75**: The class was not found in the diagnostic description. Ensure that the class qualifiers is defined in the diagnostic description.
- **-74**: Creation of the PDU bytes for a diagnostic object failed! Make sure that all parameters in the object are set to valid values.
- **-73**: During processing a negative response was received. Ensure that the ECU responds correctly.
- **-72**: No key could be calculated. Ensure that the correct Seed & Key DLL is configured.
- **-71**: The key was not accepted. Ensure that the correct Seed & Key DLL is configured.
- **-70**: The diagnostic object is too small. Check the index used.
- **-199**: The authentication tool is not properly configured.
- **-198**: Authentication was rejected. Ensure that there is no other task running in parallel.
- **-197**: This mode is not implemented.
- **-196**: Invalid handle.
- **-195**: Error in security add-on. Check the backend tool logs for potential problems.
- **-194**: Security not usable. Check whether a Security Profile supporting diagnostics is assigned.
- **-193**: Missing data.
- **-192**: Signal length mismatch.
- **-191**: General error.
- **-190**: Unknown file type.
- **-189**: File could not be read (e.g., due to missing permissions).
- **-188**: File could not be parsed.
- **-187**: At least one domain in variant coding could not be set.
- **-186**: Unknown/unsupported generic task parameter.
- **-185**: Invalid ECU response. Check the Trace window and verify that the ECU communication is as expected.
- **-184**: Channel not ready.
- **-183**: Invalid value.
- **-182**: Invalid serialized data.
- **-181**: The client version is not supported.
- **-180**: Timeout.
- **-179**: The task was aborted, as no measurement is running.
- **-178**: The specified job qualifier does not exist in the CDD file. Verify that a security job with the expected qualifier exists in the CDD file.
- **-177**: Interpretation error.
- **-176**: Communication error.
- **-175**: Unexpected response.

Note: For the following return values please check the security add-on and the configuration of the Security Manager.

© Vector Informatik GmbH
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3
[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)