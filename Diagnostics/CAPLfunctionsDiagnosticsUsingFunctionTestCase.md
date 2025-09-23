
## Diagnostics: Using Diagnostic Functions in Test Cases

[CAPL Functions](../CAPLfunctions.md) » [Diagnostics](CAPLfunctionsDiagnosticsOverview.md) » Using Diagnostic Functions in Test Cases

**Valid for**: CANoe DE

**Note**  
Waiting for diagnostic events is only possible in test modules! Conventional CAPL nodes continue to operate, but only by the event-driven principle.

After basic configuration of a diagnostic test module has been completed (the Target ECU can be selected in the MainTest function, for example), waiting for diagnostic events may be executed within the test module.

After a request has been sent the following phases are run through:

1. The request is sent to the ECU. Execution of the TestCase can be synchronized to the entire sending of the request using the function [`testWaitForDiagRequestSent(diagRequest request, dword timeout)`](../Test/Functions/CAPLfunctionTestWaitForDiagRequestSent.md);
2. The ECU begins to send a response to the tester, i.e. a "FirstFrame" (ISO TP) announces the arrival of the Response Primitive. Waiting for this event is executed using the function [`testWaitForDiagResponseStart(diagRequest request, dword timeout)`](../Test/Functions/CAPLfunctionTestWaitForDiagResponseStart.md); This function is also called if the entire response has arrived at once, i.e. a "SingleFrame" (ISO TP) contains the entire response.
3. The entire response has arrived at the tester, i.e. transmission of the entire response primitive has been completed. The function [`testWaitForDiagResponse(diagRequest request, dword timeout)`](../Test/Functions/CAPLfunctionTestWaitForDiagResponse.md); returns.

**Note**  
CANoe assumes the automatic handling of "Response Pending" (negative response with error code 0x78) responses of the ECU, i.e. this function does not return until another negative or positive response arrives, or until the timeout expires.

The return values of these functions conform to the following pattern:

- `< 0`: An internal error occurred, e.g. faulty configuration of the Diagnostic Layer.
- 0: The timeout was reached, i.e. the specific event did **not** occur within the specified time.
- 1: The event occurred. This may also be a negative response while waiting for a response from the ECU!

To evaluate the ECU’s response the request can be used to access the last received response:

- It is possible to determine whether a positive response was received, or else which negative response was received. The function [long diagGetLastResponseCode( diagRequest req)](Functions/CAPLfunctionDiagGetResponseCode.md); returns the error code of the last response received (for the specified request), whereby -1 stands for a positive response ("No error code").
- The parameters of the response can be accessed indirectly via the request object; i.e. no additional response object is needed. The following functions are available for this purpose; their functionality is analogous to those access functions that do not have "Resp" in their names: [long diagGetRespParameter( diagRequest req, char parameterName[], double output[])](Functions/CAPLfunctionDiagGetRespParameter.htm); These functions return -98 ("Object not found") if no response has been received for the request yet (since the last transmission).

Finally, there are yet other functions that simplify the development of test cases for diagnostics:

- It is possible to write a diagnostic object to the test report. This involves calling the function: [testReportWriteDiagObject( diagRequest req)](../Test/Functions/CAPLfunctionTestReportWriteDiagObjectTestReportWriteDiagResponse.md); The object’s contents are written to the test report file if this was activated. The message then appears in the test report file in the form of a table.
- The P2 timer that was defined in the Diagnostic Description can be polled by the function: [long diagGetP2Timeout()](Functions/CAPLfunctionDiagGetP2Timeout.md);
- Other communication parameters of the configured interface can be polled by the function: [long diagGetCommParameter( char paramName[])](Functions/CAPLfunctionDiagGetCommParameter.htm); If no parameter is found with the specified qualifiers, then -98 ("Object not found") is returned.
- It is possible to copy the contents of the last received response (for a specific request) to a response object. **Attention**: This may result in a change to the "Type" of the object (its qualifier path) and the number of its parameters! [long diagGetLastResponse( diagRequest req, diagResponse respOut)](Functions/CAPLfunctionDiagGetLastResponse.md);

**Example Test Case**  
The following test case shows the values of all possible states that may occur after a request is sent.

```plaintext
TestCase Test1()
{
   // Send Request and react to all possible cases.
   diagRequest Door.EcuIdentification_Read idReq;
   diagSendRequest( idReq);
   switch( TestWaitForDiagResponse( idReq, 200))
   {
   case 0: // Timeout: The ECU did not respond within 200 ms.
      write("No answer from ECU!");
      TestStepFail("Read ID", "No answer from ECU!");
      break;
   case 1: // response received
      TestReportWriteDiagResponse(idReq); // write response to report
      if( diagGetLastResponseCode(idReq) == -1)
      {
         // A positive response was received
         write("ECU Diagnostics Identification: %d", (long)diagGetRespParameter(idReq,"Diagnostic_Identification"));
         TestStepPass("Read ID", "Positiv response received!");
      }
      else // A negative response was received
      {
         write( "ECU Diagnostics Identification failed: 0x%x", diagGetLastResponseCode( idReq));
         TestStepFail("Read ID", "Negative response received");
      }
      break;
   default: // internal or setup error
      TestStepFail("Read ID", "Error in TestCase! Verdict unreliable.");
   }
}
```
